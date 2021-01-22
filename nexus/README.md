```bash
helm repo add oteemo-charts https://oteemo.github.io/charts
helm repo update
kubectl create ns nexus
helm install nexus oteemo-charts/sonatype-nexus --namespace nexus -f values.yml --version 4.2.0
```
