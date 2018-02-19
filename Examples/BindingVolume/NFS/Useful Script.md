# Collections of useful script related with NFS Binding

* Make sure you have install nfs client package `yum install nfs-utils nfs-utils-lib`
* Check on NFS shared mount : `showmount -e IP`
* Make sure you have exec `ls /bin/mount.nfs`
* How to mount `mount IP:Folder DestinationPath` for example `mount 192.168.30.9:/volume1/KuberData /mnt`