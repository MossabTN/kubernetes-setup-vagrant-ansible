```bash
helm repo add helm-openldap https://jp-gouin.github.io/helm-openldap/
helm repo update
kubectl create ns ldap
helm install ldap helm-openldap/openldap --namespace ldap -f values.yml --version 2.0.4
```
