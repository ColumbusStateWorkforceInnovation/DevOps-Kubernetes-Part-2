
# Deployments

### Refresher
[Deployments](https://kubernetes.io/docs/concepts/workloads/controllers/deployment/) work like ReplicaSets but with additional functionality such as like rollback. It also allows for more fine-grained control of pods.

 
## Task 2 (Create a Deployment)

We will make a `Deployment` similar to the replica set we created in task 1.

1. In the manifest `manifests/deployment_1.yml` update, it to have type `Deployment` with the name "nginx-deployment".
2. The deployment should have 2 `replicas` and the `revisionHistoryLimit` set to 3.
3. Under [strategy](https://kubernetes.io/docs/concepts/workloads/controllers/deployment/#strategy) we wil use the `RollingUpdate` strategy, with `maxSurge` = 1 and `maxUnavailable` = 0.
4. Create the deployment making sure to use the `--record` flag to keep the command as an annotation.
5. Use the `kubectl get` command to list the `ReplicaSet` that this deployment created with all its labels.
6. What do you notice about the `ReplicaSet` - what is this used for? Record your answer in the [deployment_task.md](deployment_task.md) `deployment_tasks.md` worksheet.
7. Try scaling the deployment like we did for `ReplicaSet` and record the command you used in the [deployment_task.md](deployment_task.md) `deployment_tasks.md` worksheet.

## Task 3 (Update the Deployment)

1. Change the `app.kubernetes.io/version` label from "1.0" to "2.0," making sure to apply the changes with the `--record` flag.
2. Run `kubectl get deploy,rs --show-labels`. Why are there two replica sets but only one deployment? Record your answer in the [deployment_task.md](deployment_task.md) `deployment_tasks.md` worksheet.
3. Run the command `kubectl rollout history deployment nginx-deployment` - and notice the revisions.
4. Use the command `kubectl annotate deployment/nginx-deployment kubernetes.io/change-cause="updated to version 2.0"`.
5. Repeat step 3 above and notice the changes.
6. Being specific that you want to [roll back](https://kubernetes.io/docs/concepts/workloads/controllers/deployment/#rolling-back-a-deployment) to revsion 1, do so and record the command you used in the [deployment_task.md](deployment_task.md) `deployment_tasks.md` worksheet.
7. Delete the deployment with `kubectl delete deploy nginx-deployment`.