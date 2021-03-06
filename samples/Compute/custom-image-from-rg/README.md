# Allow custom VM image from a Resoruce Group

This policy allows only usage of images from a resource group

## Try on Portal

[![Deploy to Azure](http://azuredeploy.net/deploybutton.png)](https://portal.azure.com/?feature.customportal=false&microsoft_azure_policy=true#blade/Microsoft_Azure_Policy/CreatePolicyDefinitionBlade)

## Try with PowerShell

````powershell
$definition = New-AzureRmPolicyDefinition -Name "custom-image-from-rg" -DisplayName "Allow custom VM image from a Resoruce Group" -description "This policy allows only usage of images from a resource group" -Policy 'https://raw.githubusercontent.com/Azure/azure-policy-samples/master/samples/Compute/custom-image-from-rg/azurepolicy.rules.json' -Parameter 'https://raw.githubusercontent.com/Azure/azure-policy-samples/master/samples/Compute/custom-image-from-rg/azurepolicy.parameters.json' -Mode All
$definition
$assignment = New-AzureRMPolicyAssignment -Name <assignmentname> -Scope <scope> -PolicyDefinition $definition
$assignment 
````



## Try with CLI

````cli

az policy definition create --name 'custom-image-from-rg' --display-name 'Allow custom VM image from a Resoruce Group' --description 'This policy allows only usage of images from a resource group' --rules 'https://raw.githubusercontent.com/Azure/azure-policy-samples/master/samples/Compute/custom-image-from-rg/azurepolicy.rules.json' --params 'https://raw.githubusercontent.com/Azure/azure-policy-samples/master/samples/Compute/custom-image-from-rg/azurepolicy.parameters.json' --mode All

az policy assignment create --name <assignmentname> --scope <scope> --policy "custom-image-from-rg" 

````
