# Docker Reference

## Install Jenkins:
```docker
docker run -p 8080:8080 -p 50000:50000 jenkins/jenkins:lts
```
## Start container:
```docker
docker container start [container id]
```
## Stop / remove all Docker containers
```docker
docker stop $(docker ps -a -q)
docker rm $(docker ps -a -q)
```
## Stop / remove all Docker images
```docker
docker rmi $(docker images -a -q)
```
## Install chocolatey:
Open Powershell as Admin and run below command
```shell
Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))
```
## Install Minikube
```docker
choco install minikube
choco install kubernetes-cli
minikube start
minikube dashboard
```
## Selenium Grid usign Kubernetes

```docker
kubectl create -f ./deploy.yml
kubectl create -f ./service.yml
kubectl create -f ./rep.yml
```
## Update deploment changes

kubectl apply -f ./deploy.yml --record
## Other commands
```docker
kubectl rollout status deployment selenium-hub
kubectl rollout history deployment selenium-hub
```
## Get pods and delete pods
```docker
kubectl get pods
Delete pods :  kubectl delete pods/[pod ID]
```
