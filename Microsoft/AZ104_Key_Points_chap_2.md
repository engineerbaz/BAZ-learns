
## Azure Resource Manager

Azure Resource Manager is the deployment and management service for Azure.

ARM can be used via 
- Azure Portal
- Azure CLI 
- PowerShell
- SDK
- Rest API 

There are few IaC 
- Terraform
- ARM template
- Bicep

ARM laverage RBAC for resource, RG and  subscription

- Resource can only exist in one Resource Group (RG)
- RG cant be renamed
- RG can have resources of many different types
- RG can have resources from different regions 

Only the Owner and User Access Administrator roles can create or delete management locks.

- Removing Resource Group 
`Remove-AzResourceGroup -Name "ContosoRG01"`


Management Group --> Subscription --> Resoource Group --> Resources