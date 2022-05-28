# The file contains all the configuration in a configmap for project Micflix

## Note that the "-n micflix" stands for the applied namespace "micflix"!

&nbsp;

### keycloak service config

```
kubectl -n micflix create configmap keycloak `
--from-literal DB_VENDOR=postgres `
--from-literal DB_ADDR=postgres `
--from-literal KK_TO_RMQ_URL=rabbitmq
```

&nbsp;

### movie-service service config

```
kubectl -n micflix create configmap movie-service `
--from-literal MDB_CLUSTER=mongodb1 `
--from-literal MDB_DATABASE=movies

```

&nbsp;

### user-service service config

```
kubectl -n micflix create configmap user-service `
--from-literal MDB_CLUSTER=mongodb2 `
--from-literal MDB_DATABASE=Users

```

&nbsp;

### delete configmaps

```
kubectl -n micflix delete configmap movie-service |
kubectl -n micflix delete configmap user-service |
kubectl -n micflix delete configmap keycloak

```
