# The file contains the services for project Micflix

(Note that this files uses the services .yaml files)

&nbsp;

### apply all the .yaml service files

```
kubectl -n micflix apply -f ./postgres-service.yaml  |
kubectl -n micflix apply -f ./mongodb1-service.yaml  |
kubectl -n micflix apply -f ./mongodb2-service.yaml  |
kubectl -n micflix apply -f ./streaming-platform-service.yaml  |
kubectl -n micflix apply -f ./user-service.yaml  |
kubectl -n micflix apply -f ./movie-service.yaml  |
kubectl -n micflix apply -f ./keycloak-service.yaml  |
kubectl -n micflix apply -f ./rabbitmq-service.yaml


```

&nbsp;

### or remove all the .yaml service files

```
kubectl -n micflix delete -f ./keycloak-service.yaml |
kubectl -n micflix delete -f ./user-service.yaml  |
kubectl -n micflix delete -f ./movie-service.yaml  |
kubectl -n micflix delete -f ./streaming-platform-service.yaml  |

```
