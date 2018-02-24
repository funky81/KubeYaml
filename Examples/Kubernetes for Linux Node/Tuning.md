# Collections of Tuning Scripts

To Improve Down Detection [reference website](https://fatalfailure.wordpress.com/2016/06/10/improving-kubernetes-reliability-quicker-detection-of-a-node-down/) :

1. Related Kubelet System 
change file `/etc/systemd/system/kubelet.service.d/10-kubeadm.conf` 
```
kubelet: node-status-update-frequency=2s (from 10s)
```
then do reload daemon
```
systemctl daemon-reload
systemctl restart docker
systemctl restart kubelet
```
check with `ps ax|grep kube`, will see this result
```
[root@mgmt ~]# ps ax|grep kubelet
18103 ?        Ssl    0:16 /usr/bin/kubelet --bootstrap-kubeconfig=/etc/kubernetes/bootstrap-kubelet.conf --kubeconfig=/etc/kubernetes/kubelet.conf node-status-update-frequency=10s --pod-manifest-path=/etc/kubernetes/manifests --allow-privileged=true --network-plugin=cni --cni-conf-dir=/etc/cni/net.d --cni-bin-dir=/opt/cni/bin --cluster-dns=10.96.0.10 --cluster-domain=cluster.local --authorization-mode=Webhook --client-ca-file=/etc/kubernetes/pki/ca.crt --cadvisor-port=0 --cgroup-driver=systemd --rotate-certificates=true --cert-dir=/var/lib/kubelet/pki
```

2. Related Kube Controller Manager

Change following files : `/etc/kubernetes/manifests/kube-controller-manager.yaml`
with these :

```
- --node-monitor-period=2s
- --node-monitor-grace-period=16s
- --pod-eviction-timeout=5s
```

to make sure do kubectl describe `PodControllerManager` -n kube-system