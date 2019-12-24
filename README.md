# azuredemos
rgname=IgniteUpdateRG
location=westeurope
aksname=IgniteUpdateAKS
az group create -n $rgname -l $location
az aks create -g $rgname -n $aksname -l $location --disable-rbac --generate-ssh-keys
az aks use-dev-spaces -g $rgname -n $aksname --space dev --yes
