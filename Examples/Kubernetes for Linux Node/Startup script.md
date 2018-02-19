# Script for Startup w/ Centos 7

Activate execute mode for rc.local by execute `chmod a+x /etc/rc.local` command

then modify rc.local file and add following code

```
swapoff -a
setenforce 0
systemctl stop firewalld
systemctl start docker
systemctl start kubelet
```

