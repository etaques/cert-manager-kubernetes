To install certificate at one domain on kubernetes cluster needs:

### 1 - create on kubernetes cluster one "cluster issuer" at your app namespace

kubectl apply -f cluster-issuer.yaml -n observability

### check it:
```
kubectl get clusterissuer -n observability

kubectl -n observability describe clusterissuer letsencrypt-prod
```


### 2 - create on kubernetes cluster respective certificate for that domain

```
kubectl apply -f certificate-grafana.yml -n observability
```

### check it:

```
kubectl get certificates -n observability

kubectl describe certificate grafana-tls -n observability

```

