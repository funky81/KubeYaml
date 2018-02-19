# Install Docker for Windows Desktop

* Install Docker for Windows *currently still in edge channel* [docker website](https://www.docker.com/docker-windows)
* Activate kubernetes from [Docker Settings](https://docs.docker.com/docker-for-windows/kubernetes/)
* Run this : `[Environment]::SetEnvironmentVariable("KUBECONFIG", $HOME + ".kube\config", [EnvironmentVariableTarget]::Machine)`