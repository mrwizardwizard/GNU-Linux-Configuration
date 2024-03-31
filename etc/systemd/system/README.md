**changemac.service**

To use changemac.service

copy changemac.service to /etc/systemd/system/

then go to the console and type systemctl enable changemac.service

Don't forget to set the device name "dev wlan0" (use ifconfig or ip address to find out).

**qdisc.service**

To use qdisc.service

copy qdisc.service to /etc/systemd/system/

then go to the console and type systemctl enable qdisc.service

Don't forget to set the device name "dev wlan0" (use ifconfig or ip address to find out).

for cake, you can use flowblind if you only have one network connection, triple-isolate if you have multiple network connections opened simultaneously.

**settxpower.service**

To use settxpower.service

copy settxpower.service to /etc/systemd/system/

then go to the console and type systemctl enable settxpower.service

The lower the tx power the less the packet loss at the cost of signal range (0 = 0 dBm = 1 mW, 300 = 3 dBm = 2 mW, 500 = 5 dBm = 3 mW).

Don't forget to set the interface name $INTERFACE (use ifconfig or ip address to find out).

**staticnet-inbound.service**

To use staticnet-inbound.service

copy staticnet-inbound.service to /etc/systemd/system/

then go to the console and type systemctl enable staticnet-inbound.service

set $INTERFACE to your interface (use ifconfig or ip address to find out), set $SOURCEIP to the inbound interface IP.

**staticnet-outbound.service**

To use staticnet-outbound.service

copy staticnet-outbound.service to /etc/systemd/system/

then go to the console and type systemctl enable staticnet-outbound.service

set $INTERFACE to your interface (use ifconfig or ip address to find out), set $SOURCEIP to an IP (1.0.0.1, etc), set $DESTINATIONIP to the interfaces ip address of your NAT device (1.0.0.0, etc) this will be the gateway.
