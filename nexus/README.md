```bash
kubectl create ns nexus

helm repo add oteemo-charts https://oteemo.github.io/charts
helm install nexus oteemo-charts/sonatype-nexus --namespace nexus -f values.yml --version 5.3.5
```
