Mount  into /usr/local/etc/haproxy/
Export :  
- kubectl get deploy haproxy-prod-v1 -n prod -o yaml --export
- kubectl get service haproxy-prod-v1 -n prod -o yaml --export
- Copy your haproxy.cfg into selected mount NFS

