**ReplicaControler and ReplicaSet**

1. ReplicaSet is replacing ReplicaController. They are used to control number of replica/copies of pods in kubernetes to provide load balancing and high-availability.

2. We can create ReplicationController using yaml file. 
3. we have created a file `./resources/replication_controller.yaml`
4. To create replication controller using above file
```
kubectl create -f ./resources/replication_controller.yaml
```
5. Verify if ReplicationController is created 
```
kubectl get replicationcontroller
```
6. To see the pods created by ReplicationController
```
kubectl get pods
```
7. For replica-set it is mainly different from ReplicaController in the sense that it has a mandatory field of 'specs.selector'. ReplicationController can only manage pods that were created as a part of ReplicationControllers' defination however ReplicaSet can also manage existing pods based on labels and also create new pods based on templates.
8. we have created a file `./resources/replica_set.yaml`
9. To create ReplicaSet from above file
```
kubectl create -f ./resources/replica_set.yaml
```
10. When we need to change the number of replica's in ReplicaSet there are two methods
```
#Method 1 - update the replica count if file and apply that change 
kubectl replace -f ./resources/replica_set.yaml


#Method 2 - change the number of replica via cli command. This wont update the file.
kubectl scale --replicas=5 ./resources/replica_set.yaml
or 
kubectl scale --replicas=5 replicaset myapp-rc
```
11. To get details of replicaset or replicationcontroller
```
#Method 1: describe replicaset
kubectl describe replicaset myapp-rc

#Method 2: describe replicationcontroller
kubectl describe replicationcontroller myapp-rc

```
12. To delete replicaset and replicacontrollers
```
# To delete replicaset
kubectl delete replicaset <name_of_replicaset>

# To delete replicacontroller
kubectl delete replicacontroller <name_of_replicacontroller>
```