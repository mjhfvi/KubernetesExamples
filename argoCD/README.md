helm repo add argo https://argoproj.github.io/argo-helm
helm install argocd argo/argo-cd --set server.service.type=LoadBalancer --set server.containerPorts.server=8082

kubectl port-forward service/argocd-server -n default 8080:443
kubectl -n default get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d

https://localhost:8080/applications



helm uninstall argocd
