# DaemonSet

[see](https://kubernetes.io/docs/concepts/workloads/controllers/daemonset/) for information on DaemonSets

### refresher
Similar to ReplicaSet/Deployment except the pods are ensured to be running on all nodes that match the selector.

This is good for pods you want to run on all nodes, like for log forwarding or capturing node health

## Task 4 (Create DaemonSet)

make sure you have no pods running from previous tasks

1. We will be updating the file `manifests/daemon_1.yml`. In it update the manifest so it is of kind `DaemonSet` with name 'nginx-ds'
2. set `revisionHistoryLimit` to 3
3. The pod spec should be the same as what we used in the previous tasks, but now we will add a `nodeSelector` with `nodeType` set to 'health'
4. `apply` the manifest with the `--record` flag
5. Does anything happen? Why? Write down your reasoning in worksheet `ds_task.md`.
6. run `kubectl label node minikube nodeType=health`
7. Did anything change? Write down what happened in the worksheet `ds_task.md`. 
8. Optional - just like with deployments, see if you can update the `DaemonSet` and roll it back to a different revision
9. run `kubectl delete ds nginx-ds` to clean up

---
