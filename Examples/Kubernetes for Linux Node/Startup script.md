# Script for Startup rc.local
#!/bin/bash
swapoff -a
setenforce 0
systemctl stop firewalld
systemctl start docker
systemctl start kubelet

chmod a+x /etc/rc.local