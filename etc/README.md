**dhcpcd.conf**

Change whitelist and static routers to your default gateway address

Change domain name servers to your routers default gateway address or the local address if you are using a local dns client or the hosts file (127.0.0.1)

**fstab**

Change UUID to match your partitions UUID in lsblk -f

Change btrfs to the filesystem you are using.

Some options are btrfs specific (autodefrag,space_cache=v2,nodatacow) you can delete these if you use another filesystem.

Set hidepid=invisible for extra security (note that this can cause some software to not function properly because it hides process IDs from the user).

**hosts**

Here you can put your favourite IPs to do domain name lookups locally (or build your own local DNS server), you need to use a DNS client first to lookup domains or use the routers DNS server and then add the IPs and domain names to the hosts file.

**locale.gen**

This file defines C/POSIX as the default locale with codeset ASCII, this only supports 127 characters and only supports latin characters, but it is useful to speed up console commands (grep, etc).

**nftables.conf**

This is a basic ingress stateful firewall configuration (IPV4 only).

It only accepts packets from port 53 (DNS) and 443 (HTTPS) on inbound.

To use ingress, change NETDEVICE to the network interface name in ifconfig (wlan0, eth0, etc)

Fill in arp saddr ether xx:xx:xx:xx:xx:xx with your modem or routers ethernet MAC address (if you cannot figure out which MAC addresses to add, use wireshark to figure out how your computer is communicateing with the modem/router).

Fill in arp saddr ip with your modem or routers gateway ip address.

Check the nftables wiki link on the main page for more information.

**limits**

Change user to your username.

**resolv.conf**

Change nameserver to your routers default gateway address or 127.0.0.1 if using a dns client or the hosts file.
