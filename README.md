# argocd-kubevela-appfile

Deploy KubeVela [Appfile](https://kubevela.io/docs/developers/learn-appfile) with ArgoCD 📦

## Prerequisites

- Kubernetes Cluster (e.g. Docker Desktop Kubernetes)
  > NOTE: I recommend an **empty cluster** since following instructions might break your cluster

### Required Tools 🛠

- [Taskfile](https://taskfile.dev)
- [ArgoCD CLI](https://argo-cd.readthedocs.io/en/stable/getting_started/#2-download-argo-cd-cli)
- [Helm](https://helm.sh)
- [Helmfile](https://github.com/helmfile/helmfile)
  - [helm-diff](https://github.com/databus23/helm-diff)

## Install base components

First, we need both [Argo CD](https://github.com/argoproj/argo-cd) and [KubeVela](https://kubevela.io) in the cluster. For Argo CD, we need to configure [Config Management Plugin](https://argo-cd.readthedocs.io/en/stable/user-guide/config-management-plugins) let Argo CD know how to treat the KubeVela Appfile.

> You can check configuration in [argocd/values.yaml](./deployments/infra/argocd/values.yaml).

To install both components, run the following command in the shell:

```sh
# This command will install `Argo CD` and `KubeVela` through `Helmfile`.
task infra:deploy
```

---

## References

- [Argo CD | Plugins](https://argo-cd.readthedocs.io/en/stable/user-guide/config-management-plugins)
- [CNCF Blog | ArgoCD + KubeVela: GitOps with Developer-centric Experience](https://www.cncf.io/blog/2020/12/22/argocd-kubevela-gitops-with-developer-centric-experience)
