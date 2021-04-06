kubectl create ns argocd
helm install argo-cd charts/argo-cd/ -n argocd
kubectl port-forward svc/argo-cd-argocd-server 8080:443 -n argocd
helm template apps/ | kubectl apply -f -