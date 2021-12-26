# Kubevela

### Install 

```
helm repo add kubevela https://charts.kubevela.net/core
helm repo update
helm upgrade --create-namespace -n vela-system --install kubevela kubevela/vela-core --version 1.2.0-rc.1 --set multicluster.enabled=true --wait
helm test kubevela -n vela-system
curl -fsSl https://kubevela.io/script/install.sh | bash
```

## Deploy firt app

```
kubectl apply -f app.yaml
```

## Get components/traits json schema 

```
kubectl get configmap component-schema-webservice-v1 -n vela-system -o yaml | yq e '.data.openapi-v3-json-schema' - | jq
```