SRE-Ai-Agent

kubectl get svc argocd-server -n argocd #获取argocdpod端口

kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d; echo #获取argocd密码
