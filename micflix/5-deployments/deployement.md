# The file contains the deployment for project Micflix

(Note that this files uses the deployment .yaml files)

&nbsp;

### apply all the .yaml deployment files

```
kubectl -n micflix apply -f ./keycloak-deployment.yaml |
kubectl -n micflix apply -f ./rabbitmq-deployment.yaml |
kubectl -n micflix apply -f ./movie-service-deployment.yaml |
kubectl -n micflix apply -f ./user-service-deployment.yaml |
kubectl -n micflix apply -f ./streaming-platform-deployment.yaml


```

&nbsp;

### or remove all the .yaml deployment files

```
kubectl -n micflix delete -f ./keycloak-deployment.yaml |
kubectl -n micflix delete -f ./rabbitmq-deployment.yaml |
kubectl -n micflix delete -f ./movie-service-deployment.yaml |
kubectl -n micflix delete -f ./user-service-deployment.yaml |
kubectl -n micflix delete -f ./streaming-platform-deployment.yaml
```
