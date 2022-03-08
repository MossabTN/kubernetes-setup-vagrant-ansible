```bash
kubectl create ns sonarqube

helm repo add sonarqube https://SonarSource.github.io/helm-chart-sonarqube
helm install sonarqube sonarqube/sonarqube --namespace sonarqube -f values.yml --version 2.0.0+248

//oidc plugin
https://github.com/vaulttec/sonar-auth-oidc
```
