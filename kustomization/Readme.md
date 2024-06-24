# Source: https://trstringer.com/helm-kustomize/
helm template . > kustomization.yaml
kubectl apply -f kustomization.yaml
