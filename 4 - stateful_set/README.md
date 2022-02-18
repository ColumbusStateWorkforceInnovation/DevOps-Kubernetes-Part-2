# StatefulSets

## Refresher
[StatefulSets](https://kubernetes.io/docs/concepts/workloads/controllers/statefulset/) are valuable for applications that require one or more of the following:

* Stable, unique network identifiers.
* Stable, persistent storage.
* Ordered, graceful deployment and scaling.
* Ordered automated rolling updates.

## Task 5 (Create a StatefulSet)

1. Review the manifest in 'manifests/stateful_1.yml`.
2. Run `kubectl apply` on it, then immediately run `watch kubectl get pods,sts,pvc,pv --show-labels` to see what happens.
3. Using output from `kubectl describe sts stateful-nginx` and `kubectl get pods,sts,pvc,pv --show-labels`, describe in [ss_task.md](ss_task.md) what happened and what you noticed about the pods and the volumes for them.
4. Bump the `app.kubernetes.io/version` to "2.0", apply the change, then run `kubectl get pods,sts,pvc,pv --show-labels`. Did anything change? Why or why not? *Hint:* see [Update strategies](https://kubernetes.io/docs/concepts/workloads/controllers/statefulset/#update-strategies). Record your answer in the [ss_task.md](ss_task.md) worksheet.
5. Delete one of the pods, then immediately run `kubectl get pods --show-labels --watch`.
6. What happened and why? Record your answer in the [ss_task.md](ss_task.md) worksheet.
7. Bump the version to "3.0" and change the `updateStrategy.type` to `RollingUpdate`.
8. Apply the change, then immediately run `watch kubectl get pods,sts,pvc,pv --show-labels`. 
9. What happens this time? Record your answer in the [ss_task.md](ss_task.md) worksheet. 
10. Run `kubectl get pods,sts,pvc,pv` to see what resources exist. 
10. Clean up by running `kubectl delete sts stateful-nginx`.
11. Repeat step 10. Was everything deleted? Why or why not? Record your answer in the [ss_task.md](ss_task.md) worksheet. 
12. Clean up the storage by running:
 ```
 for pvc in `kubectl get pvc -A -o jsonpath="{.items[*].metadata.name}"`; do kubectl delete pvc $pvc; done
 ```
13. Repeat step 10 and verify everything was deleted.