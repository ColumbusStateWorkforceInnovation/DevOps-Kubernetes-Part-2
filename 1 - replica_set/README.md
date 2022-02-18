# ReplicaSet

## Refresher
ReplicaSets allow users to set the desired number of replicas of a given pod(s) that match a selector. It handles the replica pod's lifecycle and ensures Kubernetes maintains the requested number of pods at all times.


## Task 1 (Create a ReplicaSet)

Your first task is to create a `ReplicaSet` of the nginx application we made earlier.

1. We will be editing `manifests/replica_1.yml`.
2. In it, update the resource to be of kind `ReplicaSet` and call it `nginx-replica`.
3. Give it `2` replicas.
4. For the template for the replica, use the nginx pod from before:
   - image : `nginx:stable-alpine`
   - container name : nginx
   - labels: app_name = nginx and env = dev
   - port : 80
5. Apply `manifests/replica_1.yml` to create the resource.
6. Run `kubectl get rs` and view the results.
7. Using [scale] command, scale up the replicas to 3 and record the command you used under "Task 1" in the [rs_task.md](rs_task.md) worksheet.
8. Create or apply the manifest `manifests/replica_2.yml` 
9. What happened? How many pods with our labels are there? Is there an event in the `ReplicaSet` that tells us? Write your findings under "Question 1" in the [rs_task.md](rs_task.md) worksheet. Hints:
   - `kubectl describe rs <name>` will show events for the resource.
   - This question could also be phrased, "Do you or do you not see a pod terminated? Why or why not?"
10. cleanup using the command `kubectl delete rs nginx-replica`.

## References:
Kubernetes [scale](https://kubernetes.io/docs/reference/kubectl/cheatsheet/#scaling-resources) command.