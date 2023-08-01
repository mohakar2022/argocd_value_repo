ArgoCD Rollout : 
1. How its works : https://argoproj.github.io/argo-rollouts/#how-does-it-work
2. Rollout Specification : https://argoproj.github.io/argo-rollouts/features/specification/


Install Canary Deployment 
ArgoCD UI : NewApp > 
cat appCreate.txt | pbcopy
Synchronize > APPLY 

Access Application : http://localhost:8081/productpage


Change rollout.yaml Image version 
git add . && git commit -m "U" && git push
Argocd UI sync
Check application : http://localhost:8081/productpage

kubectl argo rollouts get rollout rollout-canary
Full promote from UI 


# Cleanup Canary Deployment 

k delete application -n argocd canary-deployment-demo
k delete all --all -n default
k delete rollout rollout-canary
