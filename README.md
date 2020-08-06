Kind is Kubernetes in Docker. It requires Docker Desktop to run properly.

# Creating control plane node
`kind create cluster --config ./kind.control-plane.yaml`

# Creating worker node
`kind create cluster --config ./kind.worker.yaml`

# Joining a worker node to cluster
SSH into the cluster and get the token:

`kubeadm token create --print-join-command`