```bash
kubectl create ns sonarqube

helm repo add oteemo-charts https://oteemo.github.io/charts
helm install sonarqube oteemo-charts/sonarqube --namespace sonarqube -f values.yml --version 9.10.1

//oidc plugin
https://github.com/vaulttec/sonar-auth-oidc
```
