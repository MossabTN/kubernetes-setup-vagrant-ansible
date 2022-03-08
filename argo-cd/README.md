```bash
kubectl create ns argocd

helm repo add argo https://argoproj.github.io/argo-helm
helm install argocd argo/argo-cd --namespace argocd -f values.yml --version 2.17.0
```
