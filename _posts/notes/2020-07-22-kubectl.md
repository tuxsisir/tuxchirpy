---
title: "Kubectl"
date: 2020-07-22
draft: false
tags: ["devops"]
---

#### Kubectl (cube-cuttle)

- apply file
    - `$ kubectl apply -f <k8s-manifest>.yml`

- unapply / delete
    - `$ kubectl delete -f <k8s-manifest>.yml`

- get all pods
    - `$ kubectl get pods`

- get all svc
    - `$ kubectl get pods`

- get all pv (persistent volume)
    - `$ kubectl get pv`

- get all storage classes (storage classes)
    - `$ kubectl get sc`
- get all
    - `$ kubectl get pods,services,deployments,jobs,daemonset`

- delete
```
$ kubectl delete deployments --all
$ kubectl delete services --all
$ kubectl delete pods --all
$ kubectl delete daemonset --all
```

- config maps
    - `$ kubectl get cm`
- get all
    - `$ kubectl get all`

`kubectl get pods -w` # watch the pods
