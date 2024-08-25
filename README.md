# Projeto conversão de temperatura

#### Sobre o projeto

O projeto conversão de temperatura é um projeto desenvolvido em NodeJS. O projeto tem como objetivo ser um exemplo para a criação de ambiente com containers usando NodeJS.

#### Observações do projeto

A aplicação é exposta usando a porta 8080

# Docker

#### Build Image

docker build -t conversor-temperatura .

#### List All Images

docker image ls

#### Create/Run Container

docker container run -d -p 8080:8080 --name conversor-temperatura conversor-temperatura

#### Stop Container

docker container stop conversor-temperatura

#### Remove Container

docker container rm conversor-temperatura

#### Remove Image

docker image rm conversor-temperatura

#### Remove images without reference

docker image prune -f

#### List All Containers

docker ps

# Docker Registry

#### Login

docker login

#### Build Image with Docker Registry Name

docker build -t fernandorochaworld/temperature-converter:v0.1.0 .

#### Push Image

docker push fernandorochaworld/temperature-converter:v0.1.0

#### Set Tag latest

docker tag fernandorochaworld/temperature-converter:v0.1.0 fernandorochaworld/temperature-converter

#### Push Tag latest

docker push fernandorochaworld/temperature-converter

#### Run new Image

docker container run -p 8080:8080 -d fernandorochaworld/temperature-converter


# Kubernetes

    1. K3D
    https://k3d.io

    2. kubeCTL
    https://kubernetes.io/docs/tasks/tools
    
    3. VS Code Extensions for Kubernetes
    https://marketplace.visualstudio.com/items?itemName=ms-kubernetes-tools.vscode-kubernetes-tools

#### Create Cluster Kubernetes

 - servers=control-planes agents=worker-nodes

k3d cluster create
k3d cluster create my-cluster --servers 3 --agents 3
k3d cluster create my-cluster --servers 3 --agents 3 -p 30000:30000@loadbalancer

#### List Clusters

k3d cluster ls

#### List nodes from cluster

kubectl get nodes

#### Delete Cluster

k3d cluster delete


#### Kubernets Elements:
    - Pod = Smaller cluster's object, where the container runs.
    - ReplicaSet = Ensure the set number of pod's replicas are running.
    - Deployment = Manages the ReplicaSet. Updating application version without downtime.
    - Service = Service discovery, load-balance. Redirect address to replica/pod.
      1. ClusterIP = Cluster internal use.
      2. NodePort = External use by node IP.
      3. LoadBalancer = Create public IP to access the service.


#### Apply Manifest
kubectl apply -f src/k8s/deployment.yaml

#### Delete Manifest
kubectl delete -f src/k8s/deployment.yaml

#### List deployments
kubectl get deployment

#### List replicasets
kubectl get replicaset

#### List pods
kubectl get pod

#### List services
kubectl get service

#### Describe / Get Information

    kubectl describe pod \<pod-name\>
    kubectl describe replicaset \<replicaset-name\>
    kubectl describe deployment \<deployment-name\>
    kubectl describe service \<service-name\>

#### Kubctl Port-Forward
kubectl port-forward pod/\<pod-name\> 8080:8080

#### Delete Pod
kubectl delete pod \<pod-name\>

