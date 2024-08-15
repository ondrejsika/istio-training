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

Install Kiali using Helm: https://kiali.io/docs/installation/installation-guide/install-with-helm/

### Loki

```
kubectl apply -f https://raw.githubusercontent.com/istio/istio/master/samples/addons/loki.yaml
```

### Prometheus

```
kubectl apply -f https://raw.githubusercontent.com/istio/istio/master/samples/addons/prometheus.yaml
```

## Install Kiali Ingress

```
kubectl apply -f examples/kiali_ingress.yml
```

## Enable Sidecar Injection

```
kubectl label namespace default istio-injection=enabled
```
