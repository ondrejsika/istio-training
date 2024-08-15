# istio-training

## Install Istio

```
helm upgrade --install \
  istio-base \
  --repo https://istio-release.storage.googleapis.com/charts base \
  --namespace istio-system \
  --create-namespace \
  --set defaultRevision=default
```

```
helm upgrade --install \
  istiod \
  --repo https://istio-release.storage.googleapis.com/charts istiod \
  --namespace istio-system
```

## Install Extensions

### Grafana

```
kubectl apply -f https://raw.githubusercontent.com/istio/istio/master/samples/addons/grafana.yaml
```

### Jaeger

```
kubectl apply -f https://raw.githubusercontent.com/istio/istio/master/samples/addons/jaeger.yaml
```

### Kiali

```
kubectl apply -f https://raw.githubusercontent.com/istio/istio/master/samples/addons/kiali.yaml
```

### Loki

```
kubectl apply -f https://raw.githubusercontent.com/istio/istio/master/samples/addons/loki.yaml
```

### Prometheus

```
kubectl apply -f https://raw.githubusercontent.com/istio/istio/master/samples/addons/prometheus.yaml
```
