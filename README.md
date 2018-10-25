# ddwrt-armv7-iptables-tproxy
TPROXY kernel module files for DD-WRT armv7l (such as R6250, R6300v2, R7000, etc.), for shadowsocks redir UDP etc.

Enable JFFS partition on your router, and put these modules in /jffs.

Then write a startup script:
```
insmod /jffs/modules/xt_comment.ko
insmod /jffs/modules/xt_socket.ko
insmod /jffs/modules/xt_TPROXY.ko
```

The default iptables in DD-WRT may be too old to use, and you can install newer version by using the entware package manager:
```
cd /jffs
wget http://bin.entware.net/armv7sf-k3.2/installer/generic.sh
sh generic.sh
opkg update
opkg install iptables
```

Enjoy it!

Followed these build instructions: 
- https://github.com/jamesmacwhite/ipset-netgear-r7000-dd-wrt/wiki/Compiling-the-xt_set.ko-module
- https://github.com/elatov/elatov.github.io/blob/master/_posts/2015-07-21-compile-iptables-tee-module-for-dd-wrt.md
