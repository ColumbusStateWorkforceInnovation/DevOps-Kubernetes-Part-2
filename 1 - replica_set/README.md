# ReplicaSet

### refresher
ReplicaSets allow a user to set a desired number of replicas of a given pod(s) that match a selector.

 The ReplicaSet handles the replica pod's lifecycle and ensures the number requested is upheld.

 
## Task 1 (Create a ReplicaSet)

Your first task is to create a `ReplicaSet` of the nginx application we made earlier.

1. We will be editing `manifests/replica_1.yml`
2. In it update the resource to be of kind `ReplicaSet` and call it `nginx-replica`
3. Give it `2` replicas
4. For the template for the replica, use the nginx pod from before:
   - image : `nginx:stable-alpine` 
   - container name : nginx
   - labels: app_name = nginx and env = dev
   - port : 80
5. `apply` or `create` the resource
6. run `kubectl get rs` and view the results
   
7. Now, using [scale] command, scale up the replicas to 3. Save the command used in the `rs_task.md` file where appropriate

8. Now, create or apply the the manifest `manifests/replica_2.yml` 

9. What happened? How many pods with our labels are there? Is there an event in the `ReplicaSet` that tells us? Write your findings in the `rs_task.md`
   - hint - `kubectl describe rs <name>` will shows events for the resource   
10. cleanup using the command `kubectl delete rs nginx-replica`


[scale]: https://kubernetes.io/docs/reference/kubectl/cheatsheet/#scaling-resources