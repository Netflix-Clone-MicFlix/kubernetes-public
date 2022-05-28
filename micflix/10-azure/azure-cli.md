
# Azure Kubernetes steps
Runs the Azure CLI locally on docker
```
docker run -it --rm -v ${PWD}:/work -w /work --entrypoint /bin/sh mcr.microsoft.com/azure-cli
```

```
az login
```

```
RESOURCEGROUP=micflix
```

```
 az group create -n $RESOURCEGROUP -l westeurope
```

```
SERVICE_PRINCIPAL_JSON=$(az ad sp create-for-rbac --skip-assignment --name micflix-sp -o json)
```
To test this variable input the folwing command (Optional)
```
 echo $SERVICE_PRINCIPAL_JSON
```

```
SERVICE_PRINCIPAL=$(echo $SERVICE_PRINCIPAL_JSON | jq -r '.appId')
```

```
SERVICE_PRINCIPAL_SECRET=$(echo $SERVICE_PRINCIPAL_JSON | jq -r '.password')
```
Get SUBSCRIPTION ID
```
az account list -o table 
```
Copy ID value to the SUBSCRIPTION enviroment variable
```
SUBSCRIPTION= [Replace] #<-- place SUBSCRIPTION ID here!
```

```
az role assignment create --assignee $SERVICE_PRINCIPAL \
--scope "/subscriptions/$SUBSCRIPTION/resourceGroups/$RESOURCEGROUP" \
--role Contributor
```

### Generate SSH key
```
ssh-keygen -t rsa -b 4096 -N "[Replace]" -C "[Replace]" -q -f  ~/.ssh/id_rsa

cp ~/.ssh/id_rsa* .
```
### Create our cluster
```
az aks create -n micflix-cluster \
--resource-group $RESOURCEGROUP \
--location westeurope \
--kubernetes-version 1.23.5 \
--load-balancer-sku standard \
--nodepool-name default \
--node-count 1 \
--node-vm-size default  \
--node-osdisk-size 250 \
--ssh-key-value ./id_rsa.pub \
--network-plugin kubenet \
--service-principal $SERVICE_PRINCIPAL \
--client-secret "$SERVICE_PRINCIPAL_SECRET" \
--output none
```