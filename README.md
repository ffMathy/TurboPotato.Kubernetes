Kind is Kubernetes in Docker. It requires Docker Desktop to run properly.

# Creating a cluster
`kind create cluster --name my-cluster`

# Joining a worker node to cluster
SSH into the cluster and get the token:

`kubeadm tokens list`