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
