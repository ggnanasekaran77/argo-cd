# argo-cd
## install
```
kubectl create namespace argocd
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml
```

```
gcloud container clusters get-credentials cluster-1 --zone asia-southeast1-a --project focus-tree-329722 \
 && kubectl port-forward --namespace argocd $(kubectl get pod --namespace argocd --selector="app.kubernetes.io/name=argocd-server" --output jsonpath='{.items[0].metadata.name}') 8081:8080
 
kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d
 ```
