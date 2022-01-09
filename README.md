# Kubernetes

## Start cluster
 
```
k3d cluster start mycluster2
```

## Tools CLI

```
# Kustomize
curl -s "https://raw.githubusercontent.com/kubernetes-sigs/kustomize/master/hack/install_kustomize.sh"  | bash
```

## Cluster components

```
# nginx
helm upgrade --install ingress-nginx ingress-nginx \
  --repo https://kubernetes.github.io/ingress-nginx \
  --namespace ingress-nginx --create-namespace \
  -f nginx/values.yaml

```
