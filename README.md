# update-netbsd-kernel
Simple script to update NetBSD kernel to latest available


````
Usage: update-kernel
 -b back Set backup (default /ocurrent)
 -f      Force update even if kernel unchanged
 -h      This help
 -k kern Select kernel (default GENERIC)
 -n      Download to check but do not update kernel
 -t targ Set target (default /current)

update-kernel will download the latest GENERIC NetBSD kernel from
http://nyftp.netbsd.org/pub/NetBSD-daily/HEAD/latest/$(uname -m)/binary/kernel/netbsd-$KERNEL.gz,
and if it does not match /current, rename /current to /ocurrent and save
the new kernel (still gzipped) as /current.

It will call sudo if needed to update if run as non root.

It is recommended to have something similar to the following in /boot.cfg
  menu=Boot current:rndseed /var/db/entropy-file;boot current
  menu=Boot ocurrent:rndseed /var/db/entropy-file;boot ocurrent
````
