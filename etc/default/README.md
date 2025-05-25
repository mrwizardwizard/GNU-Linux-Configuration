**GRUB CMDLINE Options**

There is two sections the user can comment or uncomment based on whether they want full security kernel parameters or whether they want full performance kernel parameters, by default the security CMDLINE is uncommented, disabling security options is not recommended unless you are behind a stateful firewall, running trusted non malicious program code or on a machine that does not do any networking.

**grub**

pci=pcie_bus_perf can cause issues with some hardware (GPU lockups, etc), so pci=pcie_bus_safe is set to default, but you can try using it to see if it works with your hardware.

On some broken hardware, threadirqs needs CONFIG_X86_REROUTE_FOR_BROKEN_BOOT_IRQS=y set in the kernel config.

Use cpuidle.governor=menu for tickless and cpuidle.governor=ladder for periodic tick kernels, you can also use cpuidle.governor=teo which is another alternative tickless idle governor.

usbcore.authorized_default=0 can be used for systems (laptops, etc) that do not use any external usb devices (usb keyboards, usb mouses, usb storage drives, etc) or any internal usb devices, preventing rogue usbs from being authorized internally or externally. usbcore.authorized_default=2 can be used to unauthorize external usbs, but authorize internal usbs.

You can use lockdown=confidentiality and debugfs=off for extra security, if you do not plan to tune CFS tunables or if you change the fair.c/core.c/rt.c tunables.

You can change usbhid.mousepoll, usbhid.jspoll, usbhid.kbpoll based on millisecond values (10 = 100Hz, 8 = 125Hz, 5 = 200Hz, 4 = 250Hz, 2 = 500Hz, 1 = 1000Hz or 0 which uses your mouse, keyboard, joystick default polling rate).

To enable all cores with CPU mitigations, you can set
mds=full , mitigations=auto , mmio_stale_data=full , retbleed=auto , tsx_async_abort=full

Disabling microcode updates with dis_ucode_ldr, disables microcode stability and CPU bug fixes but also disables security fixes (better performance) and maybe at the cost of stability.

To enable minstrel for wireless (tx rate control algorithm), Set mac80211.ieee80211_default_rc_algo=minstrel_ht

Add skew_tick=1 to grubs CMDLINE options for jitter sensitive workloads (better latency) (CONFIG_MAXSMP must be enabled in the kernel config).

rodata can be set to rodata=full on arm64 for extra security.

Tune rcutree.rcu_fanout_leaf between 2-64 to the amount of CPUs you have (2 for 2 cores, etc).
