ArgoCD Rollout : 
1. How its works : https://argoproj.github.io/argo-rollouts/#how-does-it-work
2. Rollout Specification : https://argoproj.github.io/argo-rollouts/features/specification/

# Installation BlueGreen

ArgoCD UI : NewApp > 
cat appCreate.txt | pbcopy
Synchronize > APPLY 

Access Application : http://localhost:8081/productpage

Change rollout.yaml Image version 
git add . && git commit -m "U" && git push
Argocd UI sync
Check application : http://localhost:8081/productpage

kubectl argo rollouts get rollout rollout-canary


k delete application -n argocd bluegreen-deployment-demo
k delete rollout rollout-bluegreen
k delete all --all -n default
k delete virtualservice --all
k delete destinationrule --all

k get gateway
k get virtualservice
k get service
k get deployment
k get replicaset
k get destinationrule
k get application -n argocd
