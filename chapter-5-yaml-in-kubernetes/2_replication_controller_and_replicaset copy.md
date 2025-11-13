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