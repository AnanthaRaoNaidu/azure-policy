# Resource name contains resource group name

This policy requires resources to contain the resource group's name. For example, if the resource group name is testgroup, the resource names newtestgroupapp, testgroupaccount, and vmtestgroup would work, but newapp, testaccount, and groupvm would not work.

## Try on Azure Portal

[![Deploy to Azure](http://azuredeploy.net/deploybutton.png)](https://portal.azure.com/?feature.customportal=false&microsoft_azure_policy=true&microsoft_azure_policy_policyinsights=true&feature.microsoft_azure_security_policy=true&microsoft_azure_marketplace_policy=true#blade/Microsoft_Azure_Policy/CreatePolicyDefinitionBlade/uri/https%3A%2F%2Fraw.githubusercontent.com%2FAzure%2Fazure-policy%2Fmaster%2Fsamples%2FTextPatterns%contain-resource-group-name%2Fazurepolicy.json)

## Try with Azure PowerShell

````powershell
# Create the Policy Definition
$definition = New-AzureRmPolicyDefinition -Name "contain-resource-group-name" -DisplayName "Resource name contains resource group name" -description "Require resources to contain the resource group's name" -Policy 'https://raw.githubusercontent.com/Azure/azure-policy/master/samples/TextPatterns/contain-resource-group-name/azurepolicy.rules.json' -Mode ALL

# Show Definition
$definition

# Create the Policy Assignment
$assignment = New-AzureRMPolicyAssignment -Name <assignmentname> -Scope <scope> -PolicyDefinition $definition

# Show Assignment
$assignment

````

## Try with Azure CLI

````cli
# Create the Policy Definition
az policy definition create --name "contain-resource-group-name" --display-name "Resource name contains resource group name" --description "Require resources to contain the resource group's name" --rules "https://raw.githubusercontent.com/Azure/azure-policy/master/samples/TextPatterns/contain-resource-group-name/azurepolicy.rules.json" --mode ALL

# Create the Policy Assignment
az policy assignment create --name <assignmentname> --scope <scope> --policy "contain-resource-group-name"

 ````
