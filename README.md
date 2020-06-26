# Selenium Grid usign Kubernetes cluster

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
```
## Selenium hub and node deployment
```docker
kubectl create -f ./deploy.yml
kubectl create -f ./service.yml
kubectl create -f ./rep.yml
```
## Use view minikube dashboard
```docker
minikube dashboard
```
## Update deploment changes
```docker
kubectl apply -f ./deploy.yml --record
```
## Get deploment history
```docker
kubectl rollout history deployment selenium-hub
```
## Get deploment status
```docker
kubectl rollout status deployment selenium-hub
```
## Get details about pods 
```docker
kubectl describe pod
```
## Check pod status
```docker
kubectl get pods
```
## Delete pod
```docker
Delete pods :  kubectl delete pods/[pod ID]
```

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
