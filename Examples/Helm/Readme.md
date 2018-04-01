https://storage.googleapis.com/kubernetes-helm/helm-v2.8.2-linux-amd64.tar.gz

kubectl create clusterrolebinding add-on-cluster-admin \
    --clusterrole=cluster-admin \
    --serviceaccount=kube-system:default

helm init



