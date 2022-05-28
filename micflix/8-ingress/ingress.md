# The file contains the services for project Micflix

(Note that this files uses the services .yaml files)

&nbsp;
### apply all the .yaml service files

```
kubectl -n micflix apply -f ./rabbitmq-ingress.yaml |
kubectl -n micflix apply -f ./keyclaok-ingress.yaml |
kubectl -n micflix apply -f ./api-services-ingress.yaml |
kubectl -n micflix apply -f ./streaming-platform-ingress.yaml 


```

&nbsp;
### or remove all the .yaml service files

```
kubectl -n micflix delete -f ./rabbitmq-ingress.yaml |
kubectl -n micflix delete -f ./keyclaok-ingress.yaml |
kubectl -n micflix delete -f ./api-services-ingress.yaml |
kubectl -n micflix delete -f ./streaming-platform-ingress.yaml
```
