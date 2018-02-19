# Shortcut sripts

* How to exec command : `kubectl exec -it PodName -- Command` for example
`kubectl exec -it [PodName] -- /opt/mssql-tools/bin/sqlcmd -S localhost -U sa -P [Password]`
* How to export deployment into yaml `kubectl get deployment PodName --export -o yaml`
* How to export service into yaml `kubectl get service PodName --export -o yaml`