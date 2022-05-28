#https://app.datadoghq.com/account/settings#agent/kubernetes

&nbsp;
### apply all the .yaml service acount files
```
kubectl -n micflix create -f ./datadog-service-acount.yaml

```
&nbsp;
### apply all the .yaml service files
```
kubectl -n micflix create -f ./datadog-agent.yaml
```
&nbsp;
### delete all the .yaml service files
```
kubectl -n micflix delete -f ./datadog-service-acount.yaml |
kubectl -n micflix delete -f ./datadog-agent.yaml

```