## NOTE 
- Working with pod 
```bash 

# imperative approach 
kubectl run demo-nginx --image=nginx:latest 

kubectl apply -f pod.yaml 

kubectl get pod  -w    # watch it in realtime 
watch kubectl get pod # watch it in realtime 2s refresh


kubectl logs -f pod-name 
kubectl describe pod-name 
kubectl get pod -o wide 
curl PORT_IP
```

- Replicaset 
Control how many identical pods are running 
```bash
kubectl get rs 
kubectl delete rs rs-name
watch kubectl get pod 
kubectl delete pod <pod-name> 


```
- **Deployment: Replicaset + Stategies**
    - **RollingUpdates** (default): 
        - `maxSurge` , `maxUnavailability` 
        - Update from old pod to new pod one by one , until all old pod has been replaced with new one. 
        - for Prod
    - **Recreate** : Delete old pods, and create a new one (Recreate ) 
        - for Dev 
    - Customized: 
        - Blue/Green 
        - Canary 

*** 
