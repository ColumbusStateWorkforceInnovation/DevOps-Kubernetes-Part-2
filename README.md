# Infrastructure Automation Kubernetes Lab 5

## Introduction

We will be going over some higher level abstractions available to us in Kubernetes. Make sure you have read the slides before going through this so you have a general understanding. 

Examples from class can be found [here](https://github.com/ColumbusStateWorkforceInnovation/infrastructure-kubernetes-week2-examples)


## Objectives

In this guide we will go over Workloads, which are the higher level kubernetes objects that manage pods or other higher level objects.

Make sure you have read the slides before going through this so you have a general understanding. 


---
## Getting Started:

1 - Copy the starter code from here into a new, private repository in your personal GitHub account. When adding a collaborator, be sure to add me ("cscc-luke-rouker").


2 - You need minikube up and running before going through the examples.

Start minikube using the command:
```
$ minikube start
```

If you do not have this setup please go to the [pre-lab] and follow those instructions before continuing.

Please make sure your minikube is cleaned, by deleting all contexts, resources, configs, pods, and namespaces made.

You can do it using the `kubectl delete <resource> <name>` command or go with the scorched earth method and run ...

```
$ minikube stop
$ minikube delete
$ minikube start
```

---

## Understanding the Starter Code
This repository contains 5 exercises/tasks. They are to be done in order.
1. replica_set
2. deployment 
3. daemon_set
4. stateful_set
5. jobs

Within each directory, there is a readme with the excerise. Follow the directions, and update (if required) the provided manifest in each task directory under manifests. There is also maybe a file in each directory where you may be asked to record some information while doing the excerise.


---

## Completing the Assignment


### 1 - Go through examples

Go through each of the directories provided, and complete the tasks. You will be updating the manifests and recording any questions asked in provided files within each directory.

The general manifest structures have been provided for ease of use, you are required to update it according to the task.

---


## Submitting Your Work

1-  Publish your repository as a private repo, and ensure that you have pushed the latest version

2-  Submit the assignment in Blackboard with the link to your repo


[pre-lab]: https://github.com/cscc-afarag/kubernetes-week-1/blob/master/ENV_SETUP.md
