```bash
helm repo add jetstack https://charts.jetstack.io
helm repo update
kubectl create ns --namespace cert-manager
helm install cert-manager jetstack/cert-manager --namespace cert-manager --version v1.1.0 --set installCRDs=true


kubectl apply -f issuer.yml
```