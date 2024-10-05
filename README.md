# argocd

kubectl create ns argocd
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml

kubectl patch cm/argocd-cm --type=merge -n argocd --patch-file argocd/manifests/patch-argocd-cm.yaml

kubectl port-forward svc/argocd-server -n argocd 8080:443\n
 
argocd admin initial-password -n argocd
argocd login localhost:8080
argocd account update-password

