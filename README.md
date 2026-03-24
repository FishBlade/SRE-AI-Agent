# SRE-Ai-Agent 部署与访问指南
快速操作命令
1. 获取服务与端口
bash
复制
# 查看服务端口绑定
kubectl get svc
2. 获取 ArgoCD 凭据
bash
复制
# 获取初始管理员密码
kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d; echo

访问信息:

ArgoCD: 用户名 admin，密码通过上述命令获取

Grafana: 默认用户名/密码为 admin/prom-operator

3. 查看 Agent 日志
bash
复制
# 获取 Agent Pod
AGENT_POD=$(kubectl get pods -l app=sre-agent -o jsonpath='{.items[0].metadata.name}')

# 实时查看日志
kubectl logs -f $AGENT_POD
