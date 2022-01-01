# Grafana agent

## Install

```
source .env
kubectl apply -k .
kubectl create secret generic grafana-agent --from-literal=api-key=$METRICS_PUBLISHER_API_KEY -n observability
```

## Optimize metric usage

```
sudo sh -c 'curl -LJ -o cortextool https://github.com/grafana/cortex-tools/releases/download/v0.10.7/cortextool_0.10.7_linux_x86_64 && chmod +x cortextool && mv cortextool /usr/local/bin'
source .env
cortextool analyse grafana --address=$GRAFANA_URL --key=$GRAFANA_API_KEY
cortextool analyse prometheus --address=$PROMETHEUS_QUERY_ENDPOINT --id=$PROMETHEUS_ID --key=$PROMETHEUS_API_KEY --log.level=debug
```
