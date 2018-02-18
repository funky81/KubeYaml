Script at /root/kube - runKubeService.sh
#!/bin/bash
cd /root/kube
nohup ./start-kubelet.sh &
nohup ./start-kubeproxy.sh 10.168 &

Systemd for Centos Startup script
Examples : https://github.com/arjun024/systemd-example-startup

[Unit]
Description = Master Kubernetes Windows StartUp
After       = syslog.target

[Service]
ExecStart   = /root/kube/start.sh
Type        = forking

[Install]
WantedBy    = multi-user.target

Additional for rc.local
/root/kube/start.sh &

Extra Commands
#CLUSTER_PREFIX="10.168"
#sudo iptables -t nat -F
#sudo iptables -t nat -A POSTROUTING ! -d $CLUSTER_PREFIX.0.0/16 \
#              -m addrtype ! --dst-type LOCAL -j MASQUERADE
#sudo sysctl -w net.ipv4.ip_forward=1
#sudo route add -net $CLUSTER_PREFIX.0.0 netmask 255.255.0.0 dev ens160
#sudo route add -net $CLUSTER_PREFIX.1.0 netmask 255.255.255.0 gw #$CLUSTER_PREFIX.1.2 dev ens160