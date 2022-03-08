```bash
kubectl create ns nfs-external-provisioner

helm repo add ckotzbauer https://ckotzbauer.github.io/helm-charts
helm install nfs-client-provisioner ckotzbauer/nfs-client-provisioner --namespace nfs-external-provisioner --set nfs.server=192.168.50.8 --set nfs.path=/opt/nfs --set storageClass.defaultClass=true
```
