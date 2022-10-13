## 1. Kernel Latency Tracker 

There was a latency tracker repository created by [efficiOS](https://github.com/efficios) developer [Julien Desfossez](https://github.com/jdesfossez).

	First, please look at the code if it would satisfy our need of determining thread run queue latency. 

- [https://github.com/efficios/latency-tracker](https://github.com/efficios/latency-tracker)

There is also a companion repository utilizing [latency-tracker](https://github.com/efficios/latency-tracker)

- [https://github.com/fdoray/latency_tracker_demo/fdoray/latency_tracker_demo](https://github.com/fdoray/latency_tracker_demo/fdoray/latency_tracker_demo)

In there, there are several scripts you can run for measuring kernelspace latency. If you look at this file, 

- [scripts/trace.sh](https://github.com/fdoray/latency_tracker_demo/blob/master/scripts/trace.sh)

You will see that, there are kernel events listed as
- `syscall_latency`
- `syscall_latency_stack`

But, these kernel events are not listed when calling 

```bash
lttng list -k
```

You can find full list [here](/lttng-latency-tracker-report-2022-oct/lttng#list-kernel-events).

So, the kernel events come from [latency-tracker](https://github.com/efficios/latency-tracker). 

```bash
git clone https://github.com/efficios/latency-tracker
cd latency-tracker
```

I changed the makefile to remove warnings.

```diff
diff --git a/Makefile b/Makefile
index 82c63b7..fd83243 100644
--- a/Makefile
+++ b/Makefile
@@ -4,7 +4,7 @@ TOP_LT_MODULES_DIR := $(shell dirname $(lastword $(MAKEFILE_LIST)))
 
 include $(TOP_LT_MODULES_DIR)/Makefile.ABI.workarounds
 
-ccflags-y += -I$(src)/include $(EXTCFLAGS) -g -Wall
+ccflags-y += -I$(src)/include $(EXTCFLAGS) -g -Wall -Wno-implicit-function-declaration -Wno-incompatible-pointer-types
```

Then I tried to install the kernel modules. 

```bash
make
```

But I encountered the following error:

```c
  225 |  tracker->timer.function = latency_tracker_timer_cb;
      |                          ^
/home/torsho/dev/latency-tracker/tracker.c:228:16: error: ‘struct timer_list’ has no member named ‘data’
  228 |  tracker->timer.data = (unsigned long) tracker;
      |                ^
/home/torsho/dev/latency-tracker/tracker.c: In function ‘latency_tracker_create’:
make[2]: *** [scripts/Makefile.build:270: /home/torsho/dev/latency-tracker/tracker.o] Error 1
make[1]: *** [Makefile:1762: /home/torsho/dev/latency-tracker] Error 2
make[1]: Leaving directory '/usr/src/linux-headers-5.4.0-125-generic'
make: CSE_6603*** [Makefile:73: modules] Error 2
```

Upon further digging, I found that this stems from `init_timer` function call parameter change. 

- [Relevant issue](https://github.com/efficios/latency-tracker/issues/14)

## 2. Linux Kernel 4.14 `init_timer` deprecation

Here is a bunch of wifi drivers being broken on `June 2018`,

- [No wifi rtl8812au on Ubuntu 18.04](https://ubuntuforums.org/showthread.php?t=2394643)
- [Build failure on kernel 4.15: include/osdep_service_linux.h:274:8: error: ‘_timer’ has no member named ‘data’](https://github.com/abperiasamy/rtl8812AU_8821AU_linux/issues/241)
- [Compilation error on kernel 4.15.0-20-generic (Ubuntu 18.04)](https://github.com/gnab/rtl8812au/issues/144)

### Tentative Fixes
#### https://forum.blackmagicdesign.com/viewtopic.php?f=3&t=68382
```diff
diff -u blackmagic-io-10.9.10a2.orig/bm_util.c blackmagic-io-10.9.10a2/bm_util.c  
--- blackmagic-io-10.9.10a2.orig/bm_util.c   2018-01-08 02:46:14.000000000 +0100  
+++ blackmagic-io-10.9.10a2/bm_util.c   2018-01-31 23:27:01.543121803 +0100  
@@ -411,39 +411,45 @@  
    return jiffies_to_usecs(jiffies);  
 }  
   
+static void timer_thunk(struct timer_list* kernel_timer)  
+{  
+   bm_timer_t* timer = container_of(kernel_timer, bm_timer_t, kernel_timer);  
+   (*timer->callback)(timer->data);  
+}  
+  
 bm_timer_t* bm_timer_alloc(bm_timer_callback_t callback, void* data)  
 {  
    bm_timer_t* timer = bm_kmalloc(sizeof(bm_timer_t));  
    if (!timer)  
       return NULL;  
   
-   init_timer(timer);  
-   timer->function = (void(*)(unsigned long))callback;  
-   timer->data = (long)data;  
+   timer->callback = callback;  
+   timer->data = data;  
+   timer_setup(&timer->kernel_timer, timer_thunk, 0);  
    return timer;  
 }  
   
 void bm_timer_free(bm_timer_t* timer)  
 {  
-   del_timer(timer);  
+   del_timer(&timer->kernel_timer);  
    bm_kfree(timer);  
 }  
   
 void bm_timer_expire_in(bm_timer_t* timer, uint64_t ns)  
 {  
-   timer->expires = jiffies + (ns * HZ + NSEC_PER_SEC - 1) / NSEC_PER_SEC;  
-   add_timer(timer);  
+   timer->kernel_timer.expires = jiffies + (ns * HZ + NSEC_PER_SEC - 1) / NSEC_PER_SEC;  
+   add_timer(&timer->kernel_timer);  
 }  
   
 void bm_timer_expire_at(bm_timer_t* timer, uint64_t ns)  
 {  
-   timer->expires = (ns * HZ + NSEC_PER_SEC - 1) / NSEC_PER_SEC;  
-   add_timer(timer);  
+   timer->kernel_timer.expires = (ns * HZ + NSEC_PER_SEC - 1) / NSEC_PER_SEC;  
+   add_timer(&timer->kernel_timer);  
 }  
   
 void bm_timer_cancel(bm_timer_t* timer)  
 {  
-   del_timer(timer);  
+   del_timer(&timer->kernel_timer);  
 }  
   
 // Event waiting  
diff -u blackmagic-io-10.9.10a2.orig/bm_util.h blackmagic-io-10.9.10a2/bm_util.h  
--- blackmagic-io-10.9.10a2.orig/bm_util.h   2018-01-08 02:46:14.000000000 +0100  
+++ blackmagic-io-10.9.10a2/bm_util.h   2018-01-31 23:27:01.543121803 +0100  
@@ -112,8 +112,12 @@  
   
 // Timer  
 struct timer_list;  
-typedef struct timer_list bm_timer_t;  
 typedef void (*bm_timer_callback_t)(void*);  
+typedef struct {  
+   struct timer_list kernel_timer;  
+   bm_timer_callback_t callback;  
+   void *data;  
+} bm_timer_t;  
   
 uint64_t bm_absolute_time_us(void);
```

#### https://stackoverflow.com/questions/53801738/porting-pre-4-15-timer-code-for-mali450-gpu-kernel-driver-on-arm64
```c
struct _mali_osk_timer_t_struct {
    struct timer_list timer;
    unsigned long data;
    void (*ticked)(unsigned long data);  /* Add this */
};

#define MALI_TIMER_FLAGS 0  /* NB: choose the right bits for this! */

/* This function converts between the “new” and “old” notifications */
static void tick_trampoline(struct timer *t) {
     typedef struct _mali_osk_timer_t_struct Tldr;
     Tldr *m = container_of(t, Tldr, timer);
     m->ticked(m->data);
}
/* change this one: */
void _mali_osk_timer_setcallback(_mali_osk_timer_t *tim, _mali_osk_timer_callback_t callback, void *data)
{
    MALI_DEBUG_ASSERT_POINTER(tim);
    tim->data = (unsigned long)data;
    tim->ticked = callback; /* Note no cast */
    timer_setup(&tim->ticked, tick_trampoline, MALI_TIMER_FLAGS);
}
```

---
~torsho## 1. Kernel Latency Tracker 
