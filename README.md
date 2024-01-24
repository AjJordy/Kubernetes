# Kubernetes

- Install kind: https://kind.sigs.k8s.io/
- Install kubectl: https://kubernetes.io/pt-br/docs/tasks/tools/install-kubectl-linux/

### Extension

- VS Codes: Kubernetes by Microsoft

### Commands

- Install cluster: `kind create cluster`
- Access cluster: `kubectl cluster-info --context kind-kind`
- List Nodes: `kubectl get nodes`
- List clusters in kind: `kind get clusters`
- Delete cluster in kind: `kind delete clusters kind`
- Creating cluster with config file: `kind create cluster --config=k8s/kind.yaml --name=fullcycle`
- Accessing my cluster: `kubectl cluster-info --context kind-fullcycle`
- List all clusters: `kubectl config get-clusters`
- Change context: `kubectl config use-context CLUSTER_NAME`

- Run Go file: `go run server.go`
- Building docker image: `docker build -t ajjordy/hello-go .`
- Running container: `docker run --rm -p 80:80 ajjordy/hello-go`
- Uploading image: `docker push ajjordy/hello-go`