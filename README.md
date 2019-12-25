# azuredemos
---bash
rgname=IgniteUpdateRG
location=westeurope
aksname=IgniteUpdateAKS
az group create -n $rgname -l $location
az aks create -g $rgname -n $aksname -l $location --disable-rbac --generate-ssh-keys
az aks nodepool update --enable-cluster-autoscaler -g $rgname --cluster-name $aksname --name "nodepool1" --enable-cluster-autoscaler --min-count 3 --max-count 7
az aks update --resource-group $rgname --name $aksname --update-cluster-autoscaler --min-count 2 --max-count 7
---bash
