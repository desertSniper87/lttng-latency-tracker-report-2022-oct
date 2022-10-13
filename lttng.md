# Linux Tracing Toolkit (Next Generation)

## Manuals
- #lttng-create
	- https://lttng.org/man/1/lttng-create/v2.8/ 
		- **lttng-create** — Create an LTTng tracing session
- #lttng-relayd
	- https://lttng.org/man/8/lttng-relayd/v2.12/
		- 

## Blog Posts
[[LTTNG Blog Posts]]

## Video

- https://av.tib.eu/media/44122

## How to install 
### Azure - Ubuntu 20



## List kernel events

```
lttng list -k
```

Result:

```

Kernel events:
-------------
      lttng_logger (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      asoc_snd_soc_bias_level_start (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      asoc_snd_soc_bias_level_done (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      asoc_snd_soc_dapm_start (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      asoc_snd_soc_dapm_done (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      asoc_snd_soc_dapm_widget_power (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      asoc_snd_soc_dapm_widget_event_start (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      asoc_snd_soc_dapm_widget_event_done (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      asoc_snd_soc_dapm_walk_done (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      asoc_snd_soc_dapm_path (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      asoc_snd_soc_dapm_connected (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      asoc_snd_soc_jack_irq (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      asoc_snd_soc_jack_report (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      asoc_snd_soc_jack_notify (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      block_touch_buffer (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      block_dirty_buffer (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      block_rq_requeue (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      block_rq_complete (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      block_rq_insert (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      block_rq_issue (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      block_bio_complete (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      block_bio_bounce (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      block_bio_backmerge (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      block_bio_frontmerge (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      block_bio_queue (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      block_getrq (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      block_sleeprq (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      block_plug (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      block_unplug (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      block_split (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      block_bio_remap (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      block_rq_remap (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      compaction_isolate_migratepages (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      compaction_isolate_freepages (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      compaction_migratepages (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      gpio_direction (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      gpio_value (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      irq_handler_entry (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      irq_handler_exit (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      irq_softirq_entry (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      irq_softirq_exit (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      irq_softirq_raise (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      jbd2_checkpoint (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      jbd2_start_commit (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      jbd2_commit_locking (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      jbd2_commit_flushing (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      jbd2_commit_logging (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      jbd2_drop_transaction (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      jbd2_end_commit (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      jbd2_submit_inode_data (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      jbd2_run_stats (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      jbd2_checkpoint_stats (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      jbd2_update_log_tail (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      jbd2_write_superblock (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      kmem_kmalloc (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      kmem_cache_alloc (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      kmem_kmalloc_node (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      kmem_cache_alloc_node (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      kmem_kfree (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      kmem_cache_free (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      kmem_mm_page_free (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      kmem_mm_page_free_batched (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      kmem_mm_page_alloc (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      kmem_mm_page_alloc_zone_locked (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      kmem_mm_page_pcpu_drain (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      kmem_mm_page_alloc_extfrag (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      kvm_userspace_exit (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      kvm_set_irq (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      kvm_ioapic_set_irq (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      kvm_msi_set_irq (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      kvm_ack_irq (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      kvm_mmio (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      kvm_fpu (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      kvm_age_page (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      kvm_try_async_get_page (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      kvm_async_pf_doublefault (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      kvm_async_pf_not_present (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      kvm_async_pf_ready (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      kvm_async_pf_completed (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      module_load (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      module_free (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      module_get (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      module_put (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      module_request (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      napi_poll (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      net_dev_xmit (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      net_dev_queue (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      net_if_receive_skb (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      net_if_rx (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      net_napi_gro_frags_entry (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      net_napi_gro_receive_entry (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      net_if_receive_skb_entry (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      net_if_rx_entry (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      net_if_rx_ni_entry (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      net_if_receive_skb_list_entry (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      net_napi_gro_frags_exit (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      net_napi_gro_receive_exit (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      net_if_receive_skb_exit (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      net_if_rx_exit (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      net_if_rx_ni_exit (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      net_if_receive_skb_list_exit (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      power_cpu_idle (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      power_cpu_frequency (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      power_machine_suspend (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      power_wakeup_source_activate (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      power_wakeup_source_deactivate (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      power_clock_enable (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      power_clock_disable (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      power_clock_set_rate (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      power_domain_target (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      printk_console (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      random_mix_pool_bytes (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      random_mix_pool_bytes_nolock (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      random_credit_entropy_bits (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      random_get_random_bytes (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      random_extract_entropy (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      random_extract_entropy_user (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      rcu_utilization (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      regulator_enable (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      regulator_enable_delay (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      regulator_enable_complete (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      regulator_disable (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      regulator_disable_complete (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      regulator_set_voltage (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      regulator_set_voltage_complete (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      sched_kthread_stop (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      sched_kthread_stop_ret (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      sched_waking (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      sched_wakeup (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      sched_wakeup_new (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      sched_switch (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      sched_migrate_task (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      sched_process_free (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      sched_process_exit (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      sched_wait_task (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      sched_process_wait (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      sched_process_fork (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      sched_process_exec (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      sched_stat_wait (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      sched_stat_sleep (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      sched_stat_iowait (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      sched_stat_blocked (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      sched_stat_runtime (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      sched_pi_setprio (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      scsi_dispatch_cmd_start (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      scsi_dispatch_cmd_error (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      scsi_dispatch_cmd_done (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      scsi_dispatch_cmd_timeout (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      scsi_eh_wakeup (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      signal_generate (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      signal_deliver (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      skb_kfree (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      skb_consume (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      skb_copy_datagram_iovec (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      sock_rcvqueue_full (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      sock_exceed_buf_limit (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      lttng_statedump_start (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      lttng_statedump_end (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      lttng_statedump_process_state (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      lttng_statedump_process_cgroup_ns (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      lttng_statedump_process_ipc_ns (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      lttng_statedump_process_net_ns (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      lttng_statedump_process_pid_ns (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      lttng_statedump_process_user_ns (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      lttng_statedump_process_uts_ns (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      lttng_statedump_file_descriptor (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      lttng_statedump_vm_map (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      lttng_statedump_network_interface (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      lttng_statedump_block_device (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      lttng_statedump_interrupt (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      lttng_statedump_cpu_topology (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      rpc_call_status (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      rpc_bind_status (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      rpc_connect_status (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      rpc_task_begin (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      rpc_task_run_action (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      rpc_task_complete (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      rpc_task_sleep (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      rpc_task_wakeup (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      timer_init (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      timer_start (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      timer_expire_entry (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      timer_expire_exit (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      timer_cancel (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      timer_hrtimer_init (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      timer_hrtimer_start (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      timer_hrtimer_expire_entry (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      timer_hrtimer_expire_exit (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      timer_hrtimer_cancel (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      timer_itimer_state (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      timer_itimer_expire (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      udp_fail_queue_rcv_skb (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      mm_vmscan_kswapd_sleep (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      mm_vmscan_kswapd_wake (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      mm_vmscan_wakeup_kswapd (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      mm_vmscan_direct_reclaim_begin (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      mm_vmscan_memcg_reclaim_begin (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      mm_vmscan_memcg_softlimit_reclaim_begin (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      mm_vmscan_direct_reclaim_end (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      mm_vmscan_memcg_reclaim_end (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      mm_vmscan_memcg_softlimit_reclaim_end (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      mm_vmscan_shrink_slab_start (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      mm_vmscan_shrink_slab_end (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      mm_vmscan_lru_isolate (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      mm_vmscan_writepage (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      mm_vmscan_lru_shrink_inactive (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      v4l2_dqbuf (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      v4l2_qbuf (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      workqueue_queue_work (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      workqueue_activate_work (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      workqueue_execute_start (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      workqueue_execute_end (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      writeback_dirty_page (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      writeback_dirty_inode_start (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      writeback_dirty_inode (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      writeback_mark_inode_dirty (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      writeback_write_inode_start (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      writeback_write_inode (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      writeback_nothread (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      writeback_queue (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      writeback_exec (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      writeback_start (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      writeback_written (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      writeback_wait (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      writeback_pages_written (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      writeback_bdi_register (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      writeback_nowork (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      writeback_wake_background (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      writeback_wake_thread (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      writeback_wake_forker_thread (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      writeback_bdi_unregister (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      writeback_thread_start (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      writeback_thread_stop (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      writeback_wbc_writepage (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      writeback_queue_io (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      writeback_global_dirty_state (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      writeback_bdi_dirty_ratelimit (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      writeback_balance_dirty_pages (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      writeback_sb_inodes_requeue (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      writeback_congestion_wait (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      writeback_wait_iff_congested (loglevel: TRACE_EMERG (0)) (type: tracepoint)
      writeback_single_inode (loglevel: TRACE_EMERG (0)) (type: tracepoint)

```


### List of kernel events

- Sheduler Events
	* [[sched_switch]]
	* sched_kthread_stop 
	* sched_kthread_stop
	* sched_waking 
	* sched_wakeup 
	* sched_wakeup_new 
	* sched_migrate_task 
	* sched_process_free 
	* sched_process_exit 
	* [[sched_wait_task]] 
	* sched_process_wait 
	* sched_process_fork 
	* sched_process_exec 
	* sched_stat_wait 
	* sched_stat_sleep 
	* sched_stat_iowait 
	* sched_stat_blocked 
	* sched_stat_runtime 
	* sched_pi_setprio
- Work Queue Events
    - workqueue_queue_work 
    - workqueue_activate_work 
    - workqueue_execute_start 
    - workqueue_execute_end 


### Reading the trace 
- [[babeltrace 2]]
- TraceCompass

## Creating live session

From #lttng-create

```
lttng [GENERAL OPTIONS] create [SESSION] --live[=DELAYUS]
      [--shm-path=PATH] [--set-url=URL | --ctrl-url=URL --data-url=URL]
```
	TCP over IPv4; the default values of **CTRLPORT** and **DATAPORT** are respectively 5342 and 5343.


