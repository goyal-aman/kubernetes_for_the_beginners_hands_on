**ReplicaControler and ReplicaSet**

1. Deployments are higher in heirarchy than ReplicaSets and ReplicaControllers. There are pods. ReplicaSet manage pods. Deployment manage ReplicaSet. (Do note that ReplicationControllers are being phased out in favor of ReplicaSet). Deployments enable rolling deployments, rollbacks, pause-release etc

2. We can create Deployement using yaml file. 
3. we have created a file `./resources/deployment.yaml`
4. To create replication controller using above file
```shell
kubectl create -f ./resources/deployment.yaml
```

Running above command created a deployment object, replicaset and corresponding pods

```shell 
NAME                                    READY   STATUS              RESTARTS   AGE
pod/myapp-deployment-66d788995c-2wf5t   1/1     Running             0          5s
pod/myapp-deployment-66d788995c-jrnn5   0/1     ContainerCreating   0          5s
pod/myapp-deployment-66d788995c-q22cr   0/1     ContainerCreating   0          5s

NAME                 TYPE        CLUSTER-IP   EXTERNAL-IP   PORT(S)   AGE
service/kubernetes   ClusterIP   10.96.0.1    <none>        443/TCP   21h

NAME                               READY   UP-TO-DATE   AVAILABLE   AGE
deployment.apps/myapp-deployment   1/3     3            1           5s

NAME                                          DESIRED   CURRENT   READY   AGE
replicaset.apps/myapp-deployment-66d788995c   3         3         1       5s
```

5. Verify if Deployment is created 
```
kubectl get deployment
```
6. To See all kubernetes objects
```
kubectl get all
```
7. To get details of deployment
```
kubectl describe deployments myapp-deployment
```
