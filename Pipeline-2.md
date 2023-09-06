## Multi State Builds
- Deploy to 2 different targets using same pipeline

- ## Approvals
- Two Stages - QA & PROD for Azure App Serviecs 
- The release pipeline we previously modified deploys to QA and production. If the deployment to QA fails, then deployment to production won't trigger. It is recommended to always verify if your app is working properly in QA or test stage before deploying to production. Adding approvals will ensure all the criteria are met before deploying to the next stage
- https://learn.microsoft.com/en-us/azure/devops/pipelines/release/define-multistage-release-process?view=azure-devops

- ## Gates
- https://learn.microsoft.com/en-us/azure/devops/pipelines/release/deploy-using-approvals?view=azure-devops

## Deployment Groups
https://learn.microsoft.com/en-us/azure/devops/pipelines/release/deployment-groups/?toc=%2Fazure%2Fdevops%2Forganizations%2Ftoc.json&view=azure-devops
