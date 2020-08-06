Kind is Kubernetes in Docker. It requires Docker Desktop to run properly.

# Creating cluster
`kind create cluster --config ./kind.yaml`

# Installing Helm
`choco install kubernetes-helm`

# Setting up Helm Bitnami repository
`helm repo add bitnami https://charts.bitnami.com/bitnami`

# Deploy Kubernetes Dashboard UI
`kubectl apply -f https://raw.githubusercontent.com/kubernetes/dashboard/v2.0.0/aio/deploy/recommended.yaml`
`kubectl proxy`

Dashboard can now be accessed: http://localhost:8001/api/v1/namespaces/kubernetes-dashboard/services/https:kubernetes-dashboard:/proxy/

JWT token for dashboard can be found in Powershell using: `kubectl -n kubernetes-dashboard describe secret $(kubectl -n kubernetes-dashboard get secret | sls admin-user | ForEach-Object { $_ -Split '\s+' } | Select -First 1)`

# Installing Wordpress to Kubernetes via Helm
`helm install some-release-name bitnami/wordpress`

# More

## Joining a worker node to cluster
SSH into the cluster and get the token:

`kubeadm token create --print-join-command`