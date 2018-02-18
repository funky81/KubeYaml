# Additional for installation
# Master Linux
# Centos 7
yum install curl git build-essential docker.io conntrack python2.7

# Windows 1709
# Every time - with every node that installed and new node
# c:\k\./AddRoutes.ps1 -MasterIp [managementIp] -Gateway [eth0/external gateway]
c:\k\./AddRoutes.ps1 -MasterIp 192.168.34.71 -Gateway 192.168.91.1