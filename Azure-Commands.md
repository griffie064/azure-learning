# Azure Command Notes – Griffin Okondo

## 1. Resource Groups
```bash
az group create --name rg-learning --location eastus
az group list --output table
az resource list --resource-group rg-learning --output table# Create container
az storage container create --name intermediate-demo --account-name griffinstorage9813 --account-key "YOUR_KEY"

# Upload blob
az storage blob upload --account-name griffinstorage9813 --account-key "YOUR_KEY" --container-name intermediate-demo --name day1-storage.txt --file day1-storage.txt

# Enable Soft Delete
az storage blob service-properties delete-policy update --account-name griffinstorage9813 --account-key "YOUR_KEY" --enable true --days-retained 7az network vnet create --resource-group rg-learning --name vnet-learning --address-prefix 10.0.0.0/16 --subnet-name subnet-web --subnet-prefix 10.0.1.0/24
az network vnet subnet create --resource-group rg-learning --vnet-name vnet-learning --name subnet-data --address-prefixes 10.0.2.0/24
az network nsg create --resource-group rg-learning --name nsg-webaz bicep version
az bicep install
az deployment group create --resource-group rg-learning --template-file main.bicep --name my-deployment
az deployment group list --resource-group rg-learning --output table
