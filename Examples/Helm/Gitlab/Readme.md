How to Use Gitlab Helm Chart 
1. Download  wget https://raw.githubusercontent.com/kubernetes/charts/master/stable/gitlab-ce/values.yaml 

2. Modify values.yaml

3. Crete this PVC first `kubectl create -f gitlab-pvc.yaml`

3. Do `helm install --name gitlab-helm --namespace devops -f values.yaml stable/gitlab-ce`