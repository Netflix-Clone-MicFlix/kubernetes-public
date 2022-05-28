# Introduction to Fluentd on Kubernetes


## We need a Kubernetes cluster


```
kind create cluster --name fluentd --image kindest/node:v1.19.1
```

```
cd .\monitoring\logging\fluentd\kubernetes\

#note: use your own tag!
docker build . -t mickeykrekels/my-projects:fluentd

#note: use your own tag!
docker push mickeykrekels/my-projects:fluentd

```

## Fluentd Namespace

```
kubectl create ns fluentd

```
## Fluentd Configmap


```
kubectl apply -f ./fluentd-configmap.yaml

```

## Fluentd Daemonset

Let's deploy our `daemonset`:

```
kubectl apply -f ./fluentd-rbac.yaml 
kubectl apply -f ./fluentd.yaml
kubectl -n fluentd get pods

```

Let's deploy our example app that writes logs to `stdout`

```
kubectl create ns elastic-kibana
kubectl -n elastic-kibana apply -f ./elastic.yaml |
kubectl -n elastic-kibana apply -f ./kibana.yaml

kubectl -n elastic-kibana get pods


kubectl -n elastic-kibana port-forward svc/kibana 5601
```