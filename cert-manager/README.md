```bash
kubectl create ns cert-manager

helm repo add jetstack https://charts.jetstack.io
helm install cert-manager jetstack/cert-manager --namespace cert-manager --version v1.7.1 --set installCRDs=true

kubectl apply -f issuer.yml
```
