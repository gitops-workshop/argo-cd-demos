# Argo CD Demos

## Set-Up

```
kubectl create ns my-app-helm
kubectl create ns my-app-kustomize
```

```
argocd login localhost:8080 --username admin --password ...
```

## UI

Watch the demo!

## CLI

```
argocd app create helm-app --repo https://github.com/gitops-workshop/argo-cd-demos.git --path helm --revision master --dest-server https://kubernetes.default.svc --dest-namespace my-app-helm
argocd app create helm-app --repo https://github.com/gitops-workshop/argo-cd-demos.git --path kustomize --revision master --dest-server https://kubernetes.default.svc --dest-namespace my-app-kustomize
```


## Declarative

```
kubectl -n argocd apply -f helm/app.yaml
```

```
kubectl -n argocd apply -f kustomize/app.yaml
```
