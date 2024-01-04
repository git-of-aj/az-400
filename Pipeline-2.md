## Multi State Builds
- specify working directory always
- config files stays in one job only.... job change config files change [no config file error gone once job is same]
- Deploy to 2 different targets using same pipeline
```yaml
stages:
- stage: A
  jobs:
  - job: A1
  - job: A2

- stage: B
  jobs:
  - job: B1
  - job: B2
```
## Demands in Agent 
```yml
pool:
  name: labs
  demands: 
  - terraform 
  - python
```
- check if software installed using `seetings => agent pool => agents => capabilities` it auto detects softwares
Technical debt is a software development analogy for the consequences of taking shortcuts or using quick but suboptimal solutions, leading to future maintenance and quality challenges

## Feature Flag and App Service Configs 
Feature flags and configuration settings serve different purposes in Azure DevOps (or any development environment). The choice between them depends on what you want to achieve and the specific use case. Let's compare them and provide use cases for each:

**Feature Flags:**

1. **Use Case:** Controlled Rollouts and A/B Testing
   - Feature flags allow you to enable or disable specific features or functionality within your application without redeploying code. This is useful for controlled rollouts and A/B testing.
   - For example, you want to release a new feature to a small subset of users to gather feedback before making it available to everyone. You can use feature flags to control which users see the new feature.

2. **Use Case:** Hotfixes and Emergency Rollbacks
   - Feature flags enable you to quickly disable problematic features in production if issues arise without having to redeploy the application.
   - For instance, if a critical bug is discovered in a feature, you can disable that feature using a feature flag until the issue is resolved.

3. **Use Case:** Gradual Feature Activation
   - Feature flags allow you to gradually activate a feature for different groups of users or under certain conditions, such as user roles, geographic locations, or specific dates.
   - Imagine you're launching a new feature in different regions one by one; you can use feature flags to control when each region gets access.

**Configuration Settings:**

1. **Use Case:** Environment-specific Configuration
   - Configuration settings are typically used for storing environment-specific parameters like database connection strings, API keys, or other settings that vary between development, testing, staging, and production environments.
   - For example, you have different database connection strings for your development, testing, and production environments, and you need to manage these separately.

2. **Use Case:** Application-Level Constants
   - Configuration settings are useful for storing constants that do not change frequently, such as default timeouts, error message templates, or application-wide settings.
   - For instance, you might have a default timeout value that is used across different parts of your application.

3. **Use Case:** Security and Sensitive Information
   - Configuration settings are appropriate for storing sensitive information like encryption keys or API secrets securely.
   - If your application interacts with external services that require authentication, you should store API keys or tokens in configuration settings.

In summary, the choice between feature flags and configuration settings in Azure DevOps depends on the specific use case:

- **Use feature flags** when you need to control the activation of features in real-time, perform gradual rollouts, or manage emergency rollbacks.
- **Use configuration settings** when you need to manage environment-specific parameters, application constants, or store sensitive information.

In many cases, you may use both feature flags and configuration settings to achieve different goals within your application.
- ## Approvals
- Two Stages - QA & PROD for Azure App Serviecs 
- The release pipeline we previously modified deploys to QA and production. If the deployment to QA fails, then deployment to production won't trigger. It is recommended to always verify if your app is working properly in QA or test stage before deploying to production. Adding approvals will ensure all the criteria are met before deploying to the next stage
- https://learn.microsoft.com/en-us/azure/devops/pipelines/release/define-multistage-release-process?view=azure-devops

- ## Gates
- https://learn.microsoft.com/en-us/azure/devops/pipelines/release/deploy-using-approvals?view=azure-devops

## Deployment Groups
https://learn.microsoft.com/en-us/azure/devops/pipelines/release/deployment-groups/?toc=%2Fazure%2Fdevops%2Forganizations%2Ftoc.json&view=azure-devops
