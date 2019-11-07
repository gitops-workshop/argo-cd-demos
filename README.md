# Argo CD Demos

## Set-Up

```
kubectl create ns my-app-helm
kubectl create ns my-app-kustomize
```

```
argocd login localhost:8080 --username admin --password ...
```

### UI

Watch the demo!

### CLI

```
argocd app create helm-app --repo https://github.com/gitops-workshop/helm.git --path my-app --revision master --dest-server https://kubernetes.default.svc --dest-namespace my-app-helm
argocd app sync helm-app
```

or

```
argocd app create kustomize-app --repo https://github.com/gitops-workshop/kustomize.git --path overlays/dev --revision master --dest-server https://kubernetes.default.svc --dest-namespace my-app-kustomize
argocd app sync kustomize-app
```

### Declarative

```
kubectl -n argocd apply -f helm/app.yaml
```

```
kubectl -n argocd apply -f kustomize/app.yaml
```

### Clean Up


```
argocd app delete helm-app
argocd app delete kustomize-app
```
