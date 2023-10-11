## Deployment  Approvals & Release Gates
https://learn.microsoft.com/en-us/azure/devops/pipelines/release/approvals/?view=azure-devops&tabs=yaml

## Azure Key Vault in pipeline
https://learn.microsoft.com/en-us/azure/devops/pipelines/release/azure-key-vault?view=azure-devops&tabs=yaml

## Deployment Paterrns

## Azure App Service Feature Flag

## Azure AUtomation - ARM, DSC, Azure AUtomate

## SonarCloud - static code analysis
https://azuredevopslabs.com/labs/vstsextend/sonarcloud/

## Pipeline Teams Integration
https://learn.microsoft.com/en-us/azure/devops/pipelines/integrations/microsoft-teams?view=azure-devops

## Artefacts
Inhouse Packages => Code once and share packages across your organization. Host your private NuGet, npm, Maven, Python, and Universal Packages with Azure Artifacts for more reliable and scalable builds.
- feeds = https://learn.microsoft.com/en-us/azure/devops/artifacts/concepts/feeds?view=azure-devops
- feed view = Feed views enable developers to share a subset of package-versions with their consumers. A common use of feed views is to share package versions that have been tested and validated but hold back on packages that are still under development and/or didn't meet a certain quality bar : https://learn.microsoft.com/en-us/azure/devops/artifacts/feeds/views?view=azure-devops&tabs=nuget
- upstream sources, you can conveniently store packages from various sources in a single feed - including those that you publish, as well as those you consume from other feeds and public registries such as NuGet.org, npmjs.com, Maven Central, and PyPI. Once upstream sources enabled, a copy of any package installed from upstream will be automatically saved to your feed

## github workflow 
```
name: workflow to deploy an ARM Template to a resource group
on: push

# CONFIGURATION
# For help, go to https://github.com/Azure/Actions

env:
  AZURE_RESOURCE_GROUP: << Azure Resource Group >>   # set this to your Azure Resource group's name  
  AZURE_SUBSCRIPTION_ID: << Subscription Id >>   # set this to your Azure Subscription Id
  
jobs:
  build-and-deploy-to-dev:
    runs-on: ubuntu-latest
    steps:
                
    # Authentication
    # Set up the following secrets in your repository: AZURE_CREDENTIALS
    # For details on usage of secrets, please refer https://help.github.com/en/actions/configuring-and-managing-workflows/creating-and-storing-encrypted-secrets
    - name: Azure Login
      uses: azure/login@v1
      with:
        creds: ${{ secrets.AZURE_CREDENTIALS  }}
    
    # Checkout
    - name: Checkout
      uses: actions/checkout@v1
        
    # Deployment of template    
    - name: Deploy ARM Template
      uses: azure/arm-deploy@v1
      with:
        # You can change these environment variables for your configuration:   AZURE_SUBSCRIPTION_ID, AZURE_RESOURCE_GROUP
        subscriptionId: ${{ env.AZURE_SUBSCRIPTION_ID }}
        resourceGroupName: ${{ env.AZURE_RESOURCE_GROUP }}
        template: $GITHUB_WORKSPACE/azuredeploy.json  # Set this to the location of your template file
        parameters: $GITHUB_WORKSPACE/azuredeploy.parameters.json # Set this to the location of your parameters file
```
## azure app insight python demo
https://learn.microsoft.com/en-us/archive/blogs/najib/monitoring-python-applications-with-azure-app-insights
- flask app demo - https://learn.microsoft.com/en-us/previous-versions/azure/azure-monitor/app/opencensus-python-request#track-flask-applications
