This is a basic stateful firewall configuration similar to the nftables configuration.

nftables is much more advanced than iptables, but iptables is still in use by many linux based firmwares and older linux kernels.

Fill in -m mac ! --mac-source xx:xx:xx:xx:xx:xx with your modem or routers ethernet MAC address (if you cannot figure out which MAC addresses to add, use wireshark to figure out how your computer is communicateing with the modem/router).
