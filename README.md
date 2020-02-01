# Kubernetes Command List

In this documents we will learn a list of kubernetes command.

# Commands

## Namespaces
Commands releated to namespaces


## 1. Create Namespace
```sh
$kubectl create namespace mynamespace
```
```sh
Output: namespace/mynamespace created
```

## 2. Show All Namespaces
```sh
$kubectl get namespaces
```
```sh
Output: 
NAME                STATUS   AGE
default             Active   40d
kube-node-lease     Active   40d
kube-public         Active   40d
kube-system         Active   40d
mynamespace         Active   3m38s
```
## 3. Show All Component of a Namespace

```sh
$kubectl get all -n mynamespace
```
```sh
Output:
```