

Automate in kubenretes 

- HPA / VPA  ( Autoscale up or scale down based on real consumptions )
> condition or metrics for determine when to scale up when to scale down ( CPUUtilization ,  Memory Utilization )

kube-scheduler:  
kube-proxy: handling networking inside the kubernetes cluster 
Pod -> container -> image 



V1 -> V2 -> V3
- rollback ( revert back )


- `self-managed` : manage the kubernetes setup by yourself 
***
Tainted Nodes 
NodeSelector 
Affinity 
    NodeAffinity 
    PodAffinity 
    PodAntiAffinity 
    .....


***
1. IaC ansible playbook ( used to create machines for setup k8s cluster  )
2. clone kubespray modified some configuration 
    - pip install -r requirement.txt 
    edit some config in here 
    - k8s-cluster.yaml (change names of cluster , max pod on kubelete)
    - addson.yaml 

    run : `ansible-playbook -i inventory.ini -b cluster.yml` 


3. configuring the kubenetes dashboards 
- create service account 
- create `clusterrolebinding` object to bind service account with the clusterrole
- create the token to acccess the kubenetes dashboards

```bash
kubectl create token
```