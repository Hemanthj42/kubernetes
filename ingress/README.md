# Commands used for the Demo

##Install Minikube
Documentation: https://kubernetes.io/docs/tasks/tools/install-minikube/
# Start Minikube Kubernetes Cluster
minikube start

#Enable NGINX Ingress controller on Minikube K8s cluster
minikube addons enable ingress

## To see whether Ingress Controller is up and running
kubectl get pods -n kube-system

## Deploying sample app
kubectl create deployment web --image=gcr.io/google-samples/hello-app:1.0

## Expose as a Service
kubectl expose deployment web --type=ClusterIP --port=8080

## To check service 
kubectl get service web

## To know node ipaddress and port numbers
minikube service web --url

## Example file
Create example-ingress.yaml from the following file:

## Create the ingress 
kubectl apply -f example-ingress.yaml

kubectl get ingress

## To modify hosts file on linux or macos
sudo vi /etc/hosts

## To install v2 version of the app
kubectl create deployment web2 --image=gcr.io/google-samples/hello-app:2.0
kubectl expose deployment web2 --port=8080 --type=ClusterIP