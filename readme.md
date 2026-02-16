# Argocd Kubernetes Gitops
## Install ArgoCD on your Cluster
```
helm repo add argo https://argoproj.github.io/argo-helm
helm repo update
kubectl create namespace argocd
helm install argocd argo/argo-cd -n argocd
```
## Access ArgoCD UI

```
kubectl port-forward svc/argocd-server -n argocd 8080:443
```
## Retrieve Credentials
```
kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d
kubectl port-forward -n argo-demo svc/dotnet-api 3000:3000
```

## API Calls

Here are commands that you can use to user via API. **Windows Users should use Git Bash**.

```bash
curl -X POST http://localhost:<port>/users \
  -H "Content-Type: application/json" \
  -d '{"userName": "Mizanus Sayed"}'

curl -X POST http://localhost:<port>/users \
  -H "Content-Type: application/json" \
  -d '{"userName": "MiLa"}'
```

To verify, you can get all grades with:
```bash
curl http://localhost:<port>/users
curl http://localhost:<port>
curl http://localhost:<port>/hello
```