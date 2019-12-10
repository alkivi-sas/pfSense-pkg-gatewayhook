# pfSense-pkg-gatewayhook
Gateway up/down hook. Runs /usr/local/etc/rc.d/rc.gateway_alarm_custom upon gateway up/down event

# Installation
1. Upload the package to pfSense
2. Run from shell:
```
pkg install pfSense-pkg-gatewayhook-0_1.txz
```
3. Edit /usr/local/etc/rc.d/rc.gateway_alarm_custom upon your needs

# Building
In case you want to build this package manually, do:
1. Grab Mk directory from https://github.com/pfsense/FreeBSD-ports for your pfSense release version. The easiest way is to use a service like http://kinolien.github.io/gitzip/
2. Upload Mk directory content to /usr/ports/Mk on your pfSense
3. Put your pfSense's FreeBSD version into /usr/include/sys/param.h:
```
# cat /usr/include/sys/param.h
#define __FreeBSD_version 1102000
```
4. Upload this repo onto your pfSense, say, in /root/gatewayhook
5. 
```
cd /root/gatewayhook
make package
```
6. The resulting package will be in /root/gatewayhook/work/pkg/ directory
