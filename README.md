# k8s-wordpress
Deploying wordpress on k8s cluster based on exercise https://kubernetes.io/docs/tutorials/stateful-application/mysql-wordpress-persistent-volume/

One command to deploy to k8s cluster:
```
kubectl apply -f ./
```

One command to delete all resources from cluster:
```
kubectl delete -f ./
```

In order to access the deployment, you can check the wordpress service:
```
kubectl get services wordpress
```
The response should look like:
```
NAME        TYPE            CLUSTER-IP   EXTERNAL-IP   PORT(S)        AGE
wordpress   LoadBalancer    10.0.0.89    <pending>     80:32406/TCP   4m
```
The service is exposed on the node port 32406.

# Settings
- In `kustomization.yaml` it sets the mysql password, change it to something more secure.
- For simplicity, it creates hostPath persistence volumes (will not work properly on multi-node clusters).
