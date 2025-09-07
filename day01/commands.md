<!-- Important commmads  -->

<!-- Create a cluster with a name -->
kind create cluster --name local

<!-- Create a cluster using a config file -->
kind create cluster --config clusters.yml --name local

<!-- List running Docker containers (Kind runs clusters inside Docker) -->
docker ps

<!-- Delete a cluster by name -->
kind delete cluster --name local

<!-- List nodes in the cluster -->
kubectl get nodes

<!-- List nodes with more details -->
kubectl get nodes -o wide
