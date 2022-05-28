# The file contains all the secrets from project Micflix
## Note that the "-n micflix" stands for the applied namespace "micflix"! 

&nbsp;
### Access the private dockerhub registry
```
kubectl -n micflix create secret docker-registry regcred --docker-server=https://index.docker.io/v1/ 
--docker-username=[Replace]  
--docker-password=[Replace]  
--docker-email=[Replace] 
```

&nbsp;
### postgres database secrets
```
kubectl -n micflix create secret generic postgres `
--from-literal POSTGRES_DB=[Replace]  `
--from-literal POSTGRES_USER=[Replace]  `
--from-literal POSTGRES_PASSWORD= [Replace] 
```

&nbsp;
### keycloak service secrets
```
kubectl -n micflix create secret generic keycloak `
--from-literal DB_DATABASE=[Replace]  `
--from-literal DB_USER=[Replace]  `
--from-literal DB_PASSWORD=[Replace]  `
--from-literal KEYCLOAK_USER=[Replace]  `
--from-literal KEYCLOAK_PASSWORD=[Replace]  `
--from-literal KK_TO_RMQ_VHOST=[Replace]  `
--from-literal KK_TO_RMQ_USERNAME=[Replace]  `
--from-literal KK_TO_RMQ_PASSWORD=[Replace] 
```

&nbsp;
### mongodb_1 database secrets
```
kubectl -n micflix create secret generic mongodb1 `
--from-literal MONGO_INITDB_ROOT_USERNAME=[Replace]  `
--from-literal MONGO_INITDB_ROOT_PASSWORD=[Replace]  

```

&nbsp;
### mongodb_2 database secrets
```
kubectl -n micflix create secret generic mongodb2 `
--from-literal MONGO_INITDB_ROOT_USERNAME=[Replace]  `
--from-literal MONGO_INITDB_ROOT_PASSWORD=[Replace]  

```

&nbsp;
### rabbitmq service secrets
```
kubectl -n micflix create secret generic rabbitmq `
--from-literal RABBITMQ_DEFAULT_USER=[Replace]  `
--from-literal RABBITMQ_DEFAULT_PASS=[Replace]  `
--from-literal RABBITMQ_DEFAULT_VHOST=[Replace]  

```

&nbsp;
### movie-service service secrets
```
kubectl -n micflix create secret generic movie-service `
--from-literal MDB_USERNAME=[Replace]  `
--from-literal MDB_PASSWORD=[Replace]  

```

&nbsp;
### user-service service secrets
```
kubectl -n micflix create secret generic user-service `
--from-literal MDB_USERNAME=[Replace]  `
--from-literal MDB_PASSWORD=[Replace]  `
--from-literal RABBITMQ_URL=amqp://[Replace]  

```

&nbsp;
### datadog secrets
```
kubectl -n micflix create secret generic datadog `
--from-literal API_KEY=[Replace]  `
--from-literal APP_KEY=[Replace]  `


```

kubectl -n micflix delete secret user-service |
kubectl -n micflix delete secret movie-service |
kubectl -n micflix delete secret mongodb2 |
kubectl -n micflix delete secret mongodb1 