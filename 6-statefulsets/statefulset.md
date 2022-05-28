# The file contains the statefulset for project Micflix
(Note that this files uses the deployment .yaml files)

&nbsp;
### apply all the .yaml statefulset files
```
kubectl -n micflix apply -f ./postgres-statefulset.yaml |
kubectl -n micflix apply -f ./mongodb1-statefulset.yaml |
kubectl -n micflix apply -f ./mongodb2-statefulset.yaml 
```


&nbsp;
### or remove all the .yaml statefulset files
```
kubectl -n micflix delete -f ./postgres-statefulset.yaml |
kubectl -n micflix delete -f ./mongodb1-statefulset.yaml |
kubectl -n micflix delete -f ./mongodb2-statefulset.yaml 
```
