Install Docker for Windows Desktop
Activate kubernetes from Docker Settings (https://docs.docker.com/docker-for-windows/kubernetes/)
Run this : [Environment]::SetEnvironmentVariable("KUBECONFIG", $HOME + ".kube\config", [EnvironmentVariableTarget]::Machine)