# Argo CD Demos

## Set-Up

```
kubectl create ns my-app-helm
kubectl create ns my-app-kustomize
```

## UI

TODO

## CLI

TODO


## Declarative

```
kubectl -n argocd apply -f helm/app.yaml
```

```
kubectl -n argocd apply -f kustomize/app.yaml
```
