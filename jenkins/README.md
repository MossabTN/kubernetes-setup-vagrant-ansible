```bash
kubectl create ns jenkins

helm repo add jenkinsci https://charts.jenkins.io/
helm install jenkins jenkinsci/jenkins --namespace jenkins -f values.yml --version 3.11.5
```
