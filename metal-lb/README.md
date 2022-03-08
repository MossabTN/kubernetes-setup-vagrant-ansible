```bash
kubectl create ns metallb-system

helm repo add metallb https://metallb.github.io/metallb
helm install metallb metallb/metallb --namespace metallb-system -f values.yml

```
