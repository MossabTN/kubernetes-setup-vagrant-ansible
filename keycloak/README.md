```bash
kubectl create ns keycloak

helm repo add bitnami https://charts.bitnami.com/bitnami
helm install keycloak bitnami/keycloak --namespace keycloak -f values.yml --version 7.0.3
```
