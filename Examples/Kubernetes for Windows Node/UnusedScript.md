watch kubectl get pod --all-namespaces

 ps ax|grep kube
 systemctl start runKube
 nano /root/kube/start-kubelet.sh

 echo '1' > /proc/sys/net/bridge/bridge-nf-call-iptables

 NW
Node IP : 10.168.1.24
Pod IP : 11.0.223.104
Cluster CIDR : 10.168.0.0/16
External : 192.168.34.71

start kubeproxy => --proxy-mode=userspace

Opsional - Linux - Network
CLUSTER_PREFIX="10.168"
sudo iptables -t nat -F
sudo iptables -t nat -A POSTROUTING ! -d $CLUSTER_PREFIX.0.0/16 \
              -m addrtype ! --dst-type LOCAL -j MASQUERADE
sudo sysctl -w net.ipv4.ip_forward=1
sudo route add -net $CLUSTER_PREFIX.0.0 netmask 255.255.0.0 dev ens160
sudo route add -net $CLUSTER_PREFIX.1.0 netmask 255.255.255.0 gw $CLUSTER_PREFIX.1.2 dev ens160

Opsional Windows - Network
c:\k\./AddRoutes.ps1 -MasterIp 192.168.34.71 -Gateway 192.168.34.1


Get-HnsNetwork | Remove-HNSNetwork
