## Deployment Paterrns

## Azure App Service Feature Flag

## Azure AUtomation - ARM, DSC, Azure AUtomate

## SonarCloud - static code analysis

## Pipeline Teams Integration

## Artefacts
Inhouse Packages => Code once and share packages across your organization. Host your private NuGet, npm, Maven, Python, and Universal Packages with Azure Artifacts for more reliable and scalable builds.
- feeds = https://learn.microsoft.com/en-us/azure/devops/artifacts/concepts/feeds?view=azure-devops
- feed view = Feed views enable developers to share a subset of package-versions with their consumers. A common use of feed views is to share package versions that have been tested and validated but hold back on packages that are still under development and/or didn't meet a certain quality bar : https://learn.microsoft.com/en-us/azure/devops/artifacts/feeds/views?view=azure-devops&tabs=nuget
- upstream sources, you can conveniently store packages from various sources in a single feed - including those that you publish, as well as those you consume from other feeds and public registries such as NuGet.org, npmjs.com, Maven Central, and PyPI. Once upstream sources enabled, a copy of any package installed from upstream will be automatically saved to your feed
