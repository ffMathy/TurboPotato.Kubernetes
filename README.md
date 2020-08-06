Kind is Kubernetes in Docker. It requires Docker Desktop to run properly.

# Creating cluster
`kind create cluster --config ./kind.yaml`

# Joining a worker node to cluster
SSH into the cluster and get the token:

`kubeadm token create --print-join-command`