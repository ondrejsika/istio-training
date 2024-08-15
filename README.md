[Ondrej Sika (sika.io)](https://sika.io) | <ondrej@sika.io>

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

## Install Grafana Ingress

```
kubectl apply -f examples/grafana_ingress.yml
```

## Enable Sidecar Injection

```
kubectl label namespace default istio-injection=enabled
```

## Install Example Application

```
helm upgrade --install \
  counter \
  --repo https://helm.sikademo.com/ \
  counter \
  --set host=counter.k8s-istio.sikademo.com
```

See:
  - https://counter.k8s-istio.sikademo.com
  - https://kiali.k8s-istio.sikademo.com/kiali/console/graph/namespaces
  - https://grafana.k8s-istio.sikademo.com/dashboards
