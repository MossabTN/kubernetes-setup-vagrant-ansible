```bash
helm repo add codecentric https://codecentric.github.io/helm-charts
helm repo update
kubectl create ns keycloak
helm install keycloak codecentric/keycloak --namespace keycloak -f values.yml --version 9.8.0
```