# StatefulSets

see [here](https://kubernetes.io/docs/tutorials/stateful-application/basic-stateful-set/) and [here](https://kubernetes.io/docs/concepts/workloads/controllers/statefulset/) for information of StatefulSets

### refresher
StatefulSets are made for pods that must persist data or keep their state. 

## Task 5 (Create StatefulSet)

1. Go over the manifest in 'manifests/stateful_1.yml`
2. run `kubectl apply` on it, then use `kubectl get pods --show-labels --watch` to see what happens

3. In your worksheet, describe what happened and what you notice about the pods and the volumes for them
  - *hint* - `kubectl describe sts stateful-nginx` `kubectl get pvc` 
4. Add a new label in the pod template - apply the change and write down what happened in the worksheet.
5. Delete one of the pods then immediately run `kubectl get pods --show-labels --watch`
6. What happened? What does `OnDelete` for `updateStrategy` do? What is another `updateStrategy` type? (read docs) - Write down your answer in the worksheet.
7. run `kubectl delete sts stateful-nginx` 

---