**Info:**

**CFS Options:**

Set kernel.sched_autogroup_enabled = 1 for throughput optimization (server workloads, desktop interactivity, etc) otherwise set to 0 for lower latency (gaming workloads, low latency workloads, realtime workloads, etc).

Set kernel.sched_child_runs_first = 0 for throughput optimization (parent process runs first before child processes) otherwise set to 1 for lower latency (child processes runs first before parent process).

Set kernel.sched_energy_aware = 1 if you use CFS on mobile devices or battery powered devices, otherwise set to 0.

**Kernel Options:**

Sysctl options kernel.panic_on_unrecovered_nmi, kernel.panic_on_io_nmi and/or kernel.unknown_nmi_panic can cause kernel panics on bootup with some hardware, they are commented by default.

Sysctl option kernel.modules_disabled = 1 is commented, if you don't use modules and compiled your kernel to load drivers into RAM first, then you can uncomment it.

kernel.randomize_va_space , kernel.stack_erasing and kernel.split_lock_mitigate can be set to 0 for better performance at the cost of less security.

**Networking Options:**

net.core.netdev_tstamp_prequeue should be set to 0 if you have more than 2 CPU cores, set to 1 if you have less than 2 CPU cores.

net.ipv4.tcp_timestamps can be set to 1 for extra security against remote attackers (usually server computers need this).

net.ipv4.tcp_congestion_control can be set to illinois (lower latency) or westwood (better throughput) for end to end tcp QoS (needed if many devices are connected to your network and to avoid bufferbloat/congestion), scalable if nobody is on your network.

net.core.default_qdisc can be set to cake if you have multiple network connections opened simultaneously.

**Tips:**

The sync; command is a useful command to write out all cached data to disk (after writeing files, etc).
