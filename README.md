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
