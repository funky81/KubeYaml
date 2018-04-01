Lesson Learned :

1. NFS Dynamic Provisioning : https://github.com/kubernetes-incubator/external-storage/tree/master/nfs-client

2. NFS Server have to no root squash (no default permission in NFS Server)

3. Storage Class Name : managed-nfs-storage

4. Kubeapps : Kubeapps up and make sure every node have kubeapi