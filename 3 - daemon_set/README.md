# DaemonSet

## Refresher
A [DaemonSet](https://kubernetes.io/docs/concepts/workloads/controllers/daemonset/) ensures that all ([or some](https://kubernetes.io/docs/concepts/workloads/controllers/daemonset/#running-pods-on-select-nodes)) Nodes run a copy of a Pod. As nodes are added to the cluster, Pods are added to them. As nodes are removed from the cluster, those Pods are garbage collected. This is good for node-oriented use cases pods like log forwarding, security scanning, or metrics collection.

## Task 4 (Create DaemonSet)

Before getting started, make sure you have no pods running from previous tasks.

1. Updating the file `manifests/daemon_1.yml` to be a `DaemonSet` with the name of 'nginx-ds'.
2. Set `revisionHistoryLimit` to 3.
3. The pod spec should be the same as what we used in the previous tasks, but now we will add a `nodeSelector` with `nodeType` set to 'health'.
4. Apply the manifest with the `--record` flag.
5. Once you apply the DaemonSet, what happens and why? Write your answers in [ds_task.md](ds_task.md).
6. Run `kubectl label node minikube nodeType=health`.
7. Did anything change? Write down what happened in [ds_task.md](ds_task.md). 
8. Optional - just like with deployments, see if you can update the `DaemonSet` and roll it back to a different revision.
9. Run `kubectl delete ds nginx-ds` to clean up.