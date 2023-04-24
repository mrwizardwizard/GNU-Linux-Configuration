**Please read the files, test and make backups before using them.**

**Navigation:**

Linux-Kernel-Configuration: https://github.com/mrwizardwizard/Linux-Kernel-Configuration
 
**Philosophy:**

This linux setup is based on ideas of obtaining more performance (more free CPU resources, etc) by disabling options (and enabling ones that are not enabled by default for certain purposes (low memory conditions, works out of the box, etc) ), configuring it in a way that it performs better and tuning options to balance and obtain stability between low latency/throughput.

Security is first before performance since it is important.

**Tips:**

If you have less than 2 CPU cores, do not use threadirqs or mesa_glthread (threads work better with multiple CPU cores).

**Testing:**

Configuration files were tested under x86-64 Gentoo Linux (OpenRC) and x86-64 Arch Linux (Systemd).

These files work best on linux distributions where you configure GNU/linux yourself.

The configuration was tested using a single application at a time to maximize latency and throughput on a very minimal arch/gentoo setup as possible.

**Troubleshooting:**

If something goes wrong, you can use a live usb linux distro to mount the partition and delete the file or change the problematic setting. You can also chroot to regenerate the grub config.

**Sources:**

man (software utility, manual pages) (Linux command)

info (software utility) (Linux command)

/usr/share/

/usr/share/doc/

Linux Kernel Documentation (linux-x.x.x/Documentation)

https://wiki.nftables.org/wiki-nftables/index.php/Main_Page
