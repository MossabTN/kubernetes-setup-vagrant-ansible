```bash
helm repo add ckotzbauer https://ckotzbauer.github.io/helm-charts
helm repo update
kubectl create ns nfs-external-provisioner
helm install nfs-client-provisioner ckotzbauer/nfs-client-provisioner --namespace nfs-external-provisioner --set nfs.server=192.168.50.8 --set nfs.path=/opt/nfs --set storageClass.defaultClass=true
```

To fix error "unexpected error getting claim reference: selfLink was empty, can't make reference" for  v1.20.0+
https://github.com/kubernetes-sigs/nfs-subdir-external-provisioner/issues/25#issuecomment-742616668
