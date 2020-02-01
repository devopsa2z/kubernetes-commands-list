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
## 3. Show All Objects of a Namespace

```sh
$kubectl get all -n mynamespace
```
```sh
Output:
NAME                         READY   STATUS    RESTARTS   AGE
pod/nginx-65f88748fd-bp7pw   1/1     Running   0          2m23s

NAME                    READY   UP-TO-DATE   AVAILABLE   AGE
deployment.apps/nginx   1/1     1            1           2m25s

NAME                               DESIRED   CURRENT   READY   AGE
replicaset.apps/nginx-65f88748fd   1         1         1       2m25s

```

kubectl get deployment -n mynamespace
## Deployment
Commands releated to Deployment


## 1. Create Deployment with a single container in `mynamespce` namespace
```sh
$kubectl create deployment nginx --image=nginx -n mynamespace
```
```sh
Output:
deployment.apps/nginx created
```
> This command will create a replica set of 1 of nging containter

## 2. List all pods in `mynamespce` namespace
```sh
$kubectl get pods -n mynamespace
```
```sh
Output:
NAME                     READY   STATUS    RESTARTS   AGE
nginx-65f88748fd-bp7pw   1/1     Running   0          4m14s

```
> command with `-o wide` will show addtional details.
```sh
$kubectl get pods -n mynamespace -o wide
```
```sh
Output:
NAME                     READY   STATUS    RESTARTS   AGE     IP              NODE                            NOMINATED NODE   READINESS GATES
nginx-65f88748fd-bp7pw   1/1     Running   0          4m27s   10.30.143.253   ip-10-30-136-116.ec2.internal   <none>           <none>
```

## 3. Export a Deployment into a YAML
```sh
$kubectl get deployments 0n mynamespace
$kubectl get delopment nginx -n mynamespace -o yaml
```
