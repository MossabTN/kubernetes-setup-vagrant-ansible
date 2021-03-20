```bash
helm repo add jenkinsci https://charts.jenkins.io/
helm repo update
kubectl create ns jenkins
helm install jenkins jenkins/jenkins --namespace jenkins -f values.yml --version 3.1.0
```