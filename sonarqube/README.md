```bash
helm repo add oteemo-charts https://oteemo.github.io/charts
helm repo update
kubectl create ns sonarqube
helm install sonarqube oteemo-charts/sonarqube --namespace sonarqube -f values.yml --version 9.2.6

//oidc plugin
https://github.com/vaulttec/sonar-auth-oidc
```
