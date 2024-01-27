# Kubernetes

- Install kind: https://kind.sigs.k8s.io/
- Install kubectl: https://kubernetes.io/pt-br/docs/tasks/tools/install-kubectl-linux/

## Extension

- VS Codes: Kubernetes by Microsoft

## Commands

Deployment > Replicaset > Pod

- Install cluster: `kind create cluster`
- Access cluster: `kubectl cluster-info --context kind-kind`
- List Nodes: `kubectl get nodes`
- List clusters in kind: `kind get clusters`
- Delete cluster in kind: `kind delete clusters kind`
- Creating cluster with config file: `kind create cluster --config=k8s/kind.yaml --name=fullcycle`
- Accessing my cluster: `kubectl cluster-info --context kind-fullcycle`
- List all clusters: `kubectl config get-clusters`
- Change context: `kubectl config use-context CLUSTER_NAME`

### Docker
- Run Go file: `go run server.go`
- Building docker image: `docker build -t ajjordy/hello-go .`
- Running container: `docker run --rm -p 80:80 ajjordy/hello-go`
- Uploading image: `docker push ajjordy/hello-go`

### Pod
- Apply a pod config file: `kubectl apply -f k8s/pod.yaml`
- Get pod infos: `kubectl get pod`
- Redirect port: `kubectl port-forward pod/server 8000:80`
- Delete pod: `kubectl delete pod server`
- Describe pod: `kubectl describe pod POD_NAME`

### Replicaset
- Apply a replicaset config file: `kubectl apply -f k8s/replicaset.yaml`
- Get replicasets: `kubectl get replicasets`

### Deployments
- Get deployments: `kubectl get deployments`
- Get history: `kubectl rollout history deployment goserver`
- Go back to last version: `kubectl rollout undo deployment go server` 

### Services
- Apply a service: `kubectl apply -f k8s/service.yaml`
- Get services info: `kubectl get services`
- Access cluster service: `kubectl port-forward svc/goserver-service 8000:80`
- Proxy: `kubectl proxy --port=8080`