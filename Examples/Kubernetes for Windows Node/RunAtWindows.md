Topology
- ClusterIP : 10.168.0.0/16
- Linux Management : 192.168.34.71 netmask 192.168.34.0/24 - 192.168.34.1
- Node Windows 1 : 192.168.34.75 netmask 192.168.34.0/24 - 192.168.34.1

Linux
#!/bin/bash
cd ~/kube
./start-kubelet.sh
./start-kubeproxy.sh 10.168

Windows
./start-kubelet.ps1 -ClusterCidr 10.168.0.0/16
./start-kubeproxy.ps1

Reference : https://docs.microsoft.com/en-us/virtualization/windowscontainers/kubernetes/getting-started-kubernetes-windows

