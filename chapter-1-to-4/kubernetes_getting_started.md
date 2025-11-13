# Kubernetes Getting Started

[Setup/Installation](./setup_and_installation.md)

***kubectl*** is cli tool to interact with minikube. ***minikube*** is a tool to run local kubernetes cluster (like running your own mini cloud on your laptop)

**Demo Minikube**

```bash
minikube start --driver=docker
minikube status  
kubectl get nodes
kubectl create deployment hello-node --image=registry.k8s.io/e2e-test-images/agnhost:2.53 -- /agnhost netexec --http-port=8080
kubectl get deployments
kubectl get pods
kubectl expose deployment hello-node --type=LoadBalancer --port=8080

# to view the service on browser with ip and port
minikube service hello-node 

# list all service
kubectl get service

# list all deployment
kubectl get deployments

# delete  service
kubectl delete serice hello-node

# delete deployment
kubectl delete deployment hello-node
```

**Demo Pods**

```bash
#create pod
kubectl run nginx --image=nginx

# list pods
kubectl get pods

# get pod details
kubectl describe pods nginx

# list pods with node details
kubectl get pods -o wide

# outputs yaml code for run command
 kubectl run redis --image=redis123 --dry-run=client -o yaml

 # apply new changes from file
 kubectl apply -f <file>.yaml
 # or there is second method, which will open vim to make any edits
 kubectl edit pods redis
```

