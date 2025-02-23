# sample-service

## kubectl commands to install ArgoCD

```bash
## Create Namespace with ArgoCD name
kubectl create namespace argocd

## Deploy ArgoCD Manifest file
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml

## Enable port forwarding to access the ArgoCD API server
kubectl port-forward svc/argocd-server -n argocd 8080:443

## Login to ArgoCD using admin user and password
kubectl get secrets -n argocd argocd-initial-admin-secret -o yaml

## Copy the Password form the data field
echo hashed-password|base64 --decode


## Set default namespace as argoCD
kubectl config set-context --current --namespace=argocd
```

