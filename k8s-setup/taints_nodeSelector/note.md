# Taints Node
- Mark node to recieive or not recieve tasks assignment ( Pod will need node to run , but not on the nodes that we tainted )
- Taint Node = remark , mark to specific that the node will no longer run any tasks from scheduler
- Typically there is **no taint** for the default workers , becuase worker need to run pods 
- Typically there is a taints for the master to prevent from running normal job or workloads to aviod being overload and overwhelm which might increase the chance of server being down.
- Affinity vs Anti-affinity
Affnity : add condition for your deployment ex. running this dployment in the same node as previous deployment.

```bash
kubectl get node
#get more detail
kubectl get node -o wide
#get with lables
kubectl get node --show-labels
#describe all nodes
kubectl describe node 
#
kubectl describe nodes| grep Taints
#
kubectl get nodes -o custom-columns=NAME:.metadata.name,TAINTS:.spec.taints
# used to taint any master 
kubectl taint node node1 node-role.kubernetes.io/control-plane=:NoSchedule
# untaint master1 , so that it can run normal workload like other 
kubectl taint node node1 node-role.kubernetes.io/control-plane-
# in order taint the worker nodes 
kubectl taint node node5 service=disabled:NoSchedule
# untaint the worker node 
kubectl taint node node5 service=disabled:-NoSchedule

#Node selector : Select a specific nodes to run the wokrloads
kubectl label nodes node1 disktype=ssd
kubectl label nodes node5 disktype=ssd
kubectl label nodes node4 disktype=hdd

```

