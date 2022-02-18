# Infrastructure Automation Kubernetes Lab 5

## Introduction

We will be going over some higher-level abstractions available to us in Kubernetes. Make sure you have read the slides before going through this to have a general understanding. 

## Objectives

This guide will go over Workloads, the higher-level Kubernetes objects that manage pods, or other higher-level objects.

Make sure you have read the slides before going through this to have a general understanding. 

---
## Getting started:

1. Copy the starter code from here into a new, private repository in your personal GitHub account. When adding a collaborator, be sure to add the instructor ("CSCC-Instructor").

2. You need minikube up and running. See [minikube start](https://minikube.sigs.k8s.io/docs/start/) for installation instructions.

3. Start minikube using the command:
    ```
    $ minikube start
    ```

4. Please ensure your minikube namespace is completely clean. You can do it using the `kubectl delete <resource> <name>` command or go with the scorched earth method and run ...

    ```
    $ minikube stop
    $ minikube delete
    $ minikube start
    ```

---

## Understanding the starter code
This repository contains five exercises/tasks. Do them in order.
1. replica_set
2. deployment 
3. daemon_set
4. stateful_set
5. jobs

Within each directory, there is a readme with the exercise. Follow the directions and update (if required) the provided manifest in each task directory under manifests. There is also a worksheet in each directory that you will use to record information and answer questions while doing the exercise.

---

## Completing the assignment

1. Create a new private repository from this template.
1. Add your instructor as a collaborator.
1. Clone your new private repo to your Columbus State Community College virtual machine.

### Go through examples

Go through each of the directories provided, and complete the tasks. You will update the manifests and record any questions asked in provided files within each directory. We provided the general manifest structures that you will update as described in the directions.

Once you are ready to submit:

1. Add, commit, and push your changes to GitHub.
1. Create a pull request.
1. Request a review from your instructor.


## Submit your work

1. From the command line at the root directory of your project execute the following command: 
    ```
    git bundle create firstname-lastname-IA-title-lab-date.bundle --all
    ```
    __NOTE:__ firstname and lastname are your first and last names, and date is in the format of mmddyyyy
    
1. Submit your lab solution in Blackboard with the link to your Pull Request as well as the bundle
file you just created.
