**qdisc**

To use qdisc (OpenRC service)

copy qdisc to /etc/init.d/

set an executable bit on qdisc (chmod +x qdisc)

then go to the console and type rc-update add qdisc default

Don't forget to set the device name "dev wlan0" (use ifconfig or ip address to find out).

for cake, you can use flowblind if you only have one network connection, flows if you have multiple network connections opened simultaneously.

**changemac**

To use changemac (OpenRC service)

copy changemac to /etc/init.d/

set an executable bit on changemac (chmod +x changemac)

then go to the console and type rc-update add changemac boot

Don't forget to set the device name "dev wlan0" (use ifconfig or ip address to find out).

**settxpower**

To use settxpower (OpenRC service)

copy settxpower to /etc/init.d/

set an executable bit on settxpower (chmod +x settxpower)

then go to the console and type rc-update add settxpower default

The lower the tx power the less the packet loss at the cost of signal range (0 = 0 dBm = 1 mW, 300 = 3 dBm = 2 mW, 500 = 5 dBm = 3 mW).

Don't forget to set the interface name $INTERFACE (use ifconfig or ip address to find out).

**staticnet-inbound**

To use staticnet-inbound (OpenRC service)

copy staticnet-inbound to /etc/init.d/

set an executable bit on staticnet-inbound (chmod +x staticnet-inbound)

then go to the console and type rc-update add staticnet-inbound default

set $INTERFACE to your interface (use ifconfig or ip address to find out), set $SOURCEIP to the inbound interface IP.

**staticnet-outbound**

To use staticnet-outbound (OpenRC service)

copy staticnet-outbound to /etc/init.d/

set an executable bit on staticnet-outbound (chmod +x staticnet-outbound)

then go to the console and type rc-update add staticnet-outbound default

set $INTERFACE to your interface (use ifconfig or ip address to find out), set $SOURCEIP to an IP (1.0.0.1, etc), set $DESTINATIONIP to the interfaces ip address of your NAT device (1.0.0.0, etc) this will be the gateway.
