# Nginx App Deploy on Local Kubernetes Cluster (KinD) with ArgoCD

### What Is Argo CD?

Argo CD is a declarative, GitOps continuous delivery tool for Kubernetes.

### Why Argo CD?

Application definitions, configurations, and environments should be declarative and version controlled. Application deployment and lifecycle management should be automated, auditable, and easy to understand.

### Setup Local Kubernetes Environment (KinD) with LoadBalancer (Metallb)

Please refer to the following github repo for setting up a local kubernetes environment using KinD and LoadBalancer using Metallb.

[Create Multi-Node Local Kubernetes Cluster (KinD) with LoadBalancer (Metallb)](https://github.com/NaumanMunir9/Create-Multi-Node-Local-Kubernetes-Cluster--KinD--with-LoadBalancer--Metallb-)

## Project WorkFlow

#### Installing ArgoCD

```shell
kubectl create namespace argocd
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml
```

#### How it works

Argo CD follows the GitOps pattern of using Git repositories as the source of truth for defining the desired application state. Kubernetes manifests can be specified in several ways:

- kustomize applications
- helm charts
- jsonnet files
- Plain directory of YAML/json manifests

Argo CD automates the deployment of the desired application states in the specified target environments. Application deployments can track updates to branches, tags, or pinned to a specific version of manifests at a Git commit.
