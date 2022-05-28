# The file contains the storage-classes for project Micflix

(Note that this files uses the services .yaml files)

&nbsp;

### apply all the .yaml storage-class file

```
kubectl -n micflix apply -f ./storage-class.yaml


```

&nbsp;

### or remove all the .yaml storage-class file

```
kubectl -n micflix delete -f ./storage-class.yaml
```
