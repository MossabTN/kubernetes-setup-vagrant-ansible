```bash
kubectl create ns keycloak

helm repo add codecentric https://codecentric.github.io/helm-charts
helm install keycloak codecentric/keycloak --namespace keycloak -f values.yml --version 9.8.0
```
