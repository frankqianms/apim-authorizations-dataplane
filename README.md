# apim-authorizations-dataplane
apim authorizations data plane

Expose API Management Authorizations on Gateway (dataplane). This is helpful when application developers want to use authorizations to enable end user scenarios. 
Comes handy with interactive scenarios esp. Static Web Apps or Mobile Applications.


The repo contains ARM templates to provision the Authorizations API and associated artifacts like policies and named values.

Assuming you have created a API Management Instance
Also create Authorization providers that you would want to use for the application development.

az deployment group create --resource-group apim-rg --template-file swa-easytokens-master.template.json --parameters swa-easytokens-parameters.json --parameters ApimServiceName=test-apim --parameters SubscriptionId=159d7683-f4a0-4b15-8ecc-8542203d3c54 --parameters ResourceGroupId=apim-rg --parameters ServiceId=test-apim --parameters ARMAPIVersion=2021-12-01-preview

Turn on System Assigned Managed Identity for APIM and give it permissions as contributor to the API Management Service. 

After the above command succefully runs you can validate by using the .http file in test folder. This requires rest client vscode extension


response：
az deployment group create --resource-group apim-cli-test-rgname --template-file swa-easytokens-master.template.json --parameters swa-easytokens-parameters.json --parameters ApimServiceName=apim-cli-test --parameters SubscriptionId=1756abc0-3554-4341-8d6a-46674962ea19 --parameters ResourceGroupId=apim-cli-test-rgname --parameters ServiceId=apim-cli-test --parameters ARMAPIVersion=2021-12-01-preview

{
  "id": "/subscriptions/1756abc0-3554-4341-8d6a-46674962ea19/resourceGroups/apim-cli-test-rgname/providers/Microsoft.Resources/deployments/swa-easytokens-master.template",
  "location": null,
  "name": "swa-easytokens-master.template",
  "properties": {
    "correlationId": "6d5d4a26-393e-44a2-8962-5867d2a59858",
    "debugSetting": null,
    "dependencies": [
      {
        "dependsOn": [
          {
            "id": "/subscriptions/1756abc0-3554-4341-8d6a-46674962ea19/resourceGroups/apim-cli-test-rgname/providers/Microsoft.Resources/deployments/namedValuesTemplate",
            "resourceGroup": "apim-cli-test-rgname",
            "resourceName": "namedValuesTemplate",
            "resourceType": "Microsoft.Resources/deployments"
          },
          {
            "id": "/subscriptions/1756abc0-3554-4341-8d6a-46674962ea19/resourceGroups/apim-cli-test-rgname/providers/Microsoft.Resources/deployments/globalServicePolicyTemplate",
            "resourceGroup": "apim-cli-test-rgname",
            "resourceName": "globalServicePolicyTemplate",
            "resourceType": "Microsoft.Resources/deployments"
          }
        ],
        "id": "/subscriptions/1756abc0-3554-4341-8d6a-46674962ea19/resourceGroups/apim-cli-test-rgname/providers/Microsoft.Resources/deployments/apisTemplate",
        "resourceGroup": "apim-cli-test-rgname",
        "resourceName": "apisTemplate",
        "resourceType": "Microsoft.Resources/deployments"
      }
    ],
    "duration": "PT1M14.822855S",
    "error": null,
    "mode": "Incremental",
    "onErrorDeployment": null,
    "outputResources": [
      {
        "id": "/subscriptions/1756abc0-3554-4341-8d6a-46674962ea19/resourceGroups/apim-cli-test-rgname/providers/Microsoft.ApiManagement/service/apim-cli-test/apis/authorizations",
        "resourceGroup": "apim-cli-test-rgname"
      },
      {
        "id": "/subscriptions/1756abc0-3554-4341-8d6a-46674962ea19/resourceGroups/apim-cli-test-rgname/providers/Microsoft.ApiManagement/service/apim-cli-test/apis/authorizations/operations/connect",
        "resourceGroup": "apim-cli-test-rgname"
      },
      {
        "id": "/subscriptions/1756abc0-3554-4341-8d6a-46674962ea19/resourceGroups/apim-cli-test-rgname/providers/Microsoft.ApiManagement/service/apim-cli-test/apis/authorizations/operations/connect/policies/policy",
        "resourceGroup": "apim-cli-test-rgname"
      },
      {
        "id": "/subscriptions/1756abc0-3554-4341-8d6a-46674962ea19/resourceGroups/apim-cli-test-rgname/providers/Microsoft.ApiManagement/service/apim-cli-test/apis/authorizations/operations/disconnect",
        "resourceGroup": "apim-cli-test-rgname"
      },
      {
        "id": "/subscriptions/1756abc0-3554-4341-8d6a-46674962ea19/resourceGroups/apim-cli-test-rgname/providers/Microsoft.ApiManagement/service/apim-cli-test/apis/authorizations/operations/disconnect/policies/policy",
        "resourceGroup": "apim-cli-test-rgname"
      },
      {
        "id": "/subscriptions/1756abc0-3554-4341-8d6a-46674962ea19/resourceGroups/apim-cli-test-rgname/providers/Microsoft.ApiManagement/service/apim-cli-test/apis/authorizations/operations/providers",
        "resourceGroup": "apim-cli-test-rgname"
      },
      {
        "id": "/subscriptions/1756abc0-3554-4341-8d6a-46674962ea19/resourceGroups/apim-cli-test-rgname/providers/Microsoft.ApiManagement/service/apim-cli-test/apis/authorizations/operations/providers/policies/policy",
        "resourceGroup": "apim-cli-test-rgname"
      },
      {
        "id": "/subscriptions/1756abc0-3554-4341-8d6a-46674962ea19/resourceGroups/apim-cli-test-rgname/providers/Microsoft.ApiManagement/service/apim-cli-test/apis/authorizations/operations/status",
        "resourceGroup": "apim-cli-test-rgname"
      },
      {
        "id": "/subscriptions/1756abc0-3554-4341-8d6a-46674962ea19/resourceGroups/apim-cli-test-rgname/providers/Microsoft.ApiManagement/service/apim-cli-test/apis/authorizations/operations/status/policies/policy",
        "resourceGroup": "apim-cli-test-rgname"
      },
      {
        "id": "/subscriptions/1756abc0-3554-4341-8d6a-46674962ea19/resourceGroups/apim-cli-test-rgname/providers/Microsoft.ApiManagement/service/apim-cli-test/apis/authorizations/schemas/62c5005501234e10ac41ef84",
        "resourceGroup": "apim-cli-test-rgname"
      },
      {
        "id": "/subscriptions/1756abc0-3554-4341-8d6a-46674962ea19/resourceGroups/apim-cli-test-rgname/providers/Microsoft.ApiManagement/service/apim-cli-test/namedValues/ARMAPIVersion",
        "resourceGroup": "apim-cli-test-rgname"
      },
      {
        "id": "/subscriptions/1756abc0-3554-4341-8d6a-46674962ea19/resourceGroups/apim-cli-test-rgname/providers/Microsoft.ApiManagement/service/apim-cli-test/namedValues/ResourceGroupId",
        "resourceGroup": "apim-cli-test-rgname"
      },
      {
        "id": "/subscriptions/1756abc0-3554-4341-8d6a-46674962ea19/resourceGroups/apim-cli-test-rgname/providers/Microsoft.ApiManagement/service/apim-cli-test/namedValues/ServiceId",
        "resourceGroup": "apim-cli-test-rgname"
      },
      {
        "id": "/subscriptions/1756abc0-3554-4341-8d6a-46674962ea19/resourceGroups/apim-cli-test-rgname/providers/Microsoft.ApiManagement/service/apim-cli-test/namedValues/SubscriptionId",
        "resourceGroup": "apim-cli-test-rgname"
      },
      {
        "id": "/subscriptions/1756abc0-3554-4341-8d6a-46674962ea19/resourceGroups/apim-cli-test-rgname/providers/Microsoft.ApiManagement/service/apim-cli-test/policies/policy",
        "resourceGroup": "apim-cli-test-rgname"
      }
    ],
    "outputs": null,
    "parameters": {
      "apimServiceName": {
        "type": "String",
        "value": "apim-cli-test"
      },
      "armapiVersion": {
        "type": "String",
        "value": "2021-12-01-preview"
      },
      "linkedTemplatesBaseUrl": {
        "type": "String",
        "value": "https://raw.githubusercontent.com/annaji-msft/apim-authorizations-dataplane/main/deploy"
      },
      "linkedTemplatesUrlQueryString": {
        "type": "String",
        "value": " "
      },
      "policyXMLBaseUrl": {
        "type": "String",
        "value": "https://raw.githubusercontent.com/annaji-msft/apim-authorizations-dataplane/main/deploy/policies"
      },
      "policyXMLSasToken": {
        "type": "String",
        "value": " "
      },
      "resourceGroupId": {
        "type": "String",
        "value": "apim-cli-test-rgname"
      },
      "serviceId": {
        "type": "String",
        "value": "apim-cli-test"
      },
      "subscriptionId": {
        "type": "String",
        "value": "1756abc0-3554-4341-8d6a-46674962ea19"
      }
    },
        "registrationState": null,
        "resourceTypes": [
          {
            "aliases": null,
            "apiProfiles": null,
            "apiVersions": null,
            "capabilities": null,
            "defaultApiVersion": null,
            "locationMappings": null,
            "locations": [
              null
            ],
            "properties": null,
            "resourceType": "deployments",
            "zoneMappings": null
          }
        ]
      }
    ],
    "provisioningState": "Succeeded",
    "templateHash": "12102748635972059567",
    "templateLink": null,
    "timestamp": "2022-08-05T07:12:23.292272+00:00",
    "validatedResources": null
  },
  "resourceGroup": "apim-cli-test-rgname",
  "tags": null,
  "type": "Microsoft.Resources/deployments"
}
