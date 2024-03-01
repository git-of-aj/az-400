## BG
- Blue-green deployment is a technique that reduces risk and downtime by running two identical environments called `blue and green`.
- Blue” (currently live) version, and the other is the “Green” (new)
- eployment and final testing stage occur in an environment that isn't live: in this example, green. Once you've deployed and thoroughly tested the software in green, switch the router or load balancer so all incoming requests go to green instead of blue.
-  it involves database schema changes, this process isn't straightforward. You probably can't swap your application
```yml
Step 1: Direct traffic to the Blue environment (v1.0).
Step 2: Deploy v2.0 to the Green environment.
Step 3: Perform tests and validations on the Green environment.
Step 4: Update the load balancer to route traffic to the Green environment (v2.0).
Step 5: Monitor the Green environment for any issues.
Step 6: If everything goes smoothly, the deployment is successful.
Step 7: If issues arise, switch back to the Blue environment.
```

## Canaries =
You have a group of users who are better at dealing with new code and issues if they arise, and these people are often called Canaries.
- A canary release is a way to identify potential problems without exposing all your end users to the issue at once.
- Canary releases can be implemented using a combination of feature toggles, traffic routing, and deployment slots.
1. You can route a percentage of traffic to a deployment slot with the new feature enabled.
2. You can target a specific user segment by using feature toggles.
- [feature flag](https://learn.microsoft.com/en-us/azure/azure-app-configuration/manage-feature-flags)
```yml
# AS IN MOBILE APPS (BETA VERSION) & OTHER SOFTWARES (PREVIEW) BUT FIRST TO INTERNAL USERS NOT END USRS
Step 1: Select a small group of users or servers (the "Canary" group).
Step 2: Deploy the new version to the Canary group while keeping the rest on the stable version.
Step 3: Monitor the Canary group for any errors, performance issues, or crashes.
Step 4: If the Canary deployment is successful, gradually increase the number of users/servers in the deployment.
Step 5: If issues arise, roll back the changes for the affected users/servers.
Step 6: Continue monitoring the entire deployment until confident in its stability.
```

## ROLLING UPDATES - MICROSERVICES
```YML
Step 1: Deploy the updated version of the container to one or more instances.
Step 2: Wait for these instances to stabilize and start serving traffic.
Step 3: If everything is functioning correctly, update the remaining instances one by one.
Step 4: Continue this process until all instances are running the new version.
Step 5: If any issues occur, pause the deployment and investigate the problem before proceeding.
```

## Dark Launching [space x uses it]
- launch it to subset of users
Usually, these users aren't aware they're being used as test users for the new feature, and often you don't even highlight the new feature to them, as such the term "Dark" launching.
Another example of dark launching is launching a new feature and using it on the backend to get metrics.

## A/B testing 
A/B testing (also known as split testing or bucket testing) compares two versions of a web page or app against each other to determine which one does better.
- A/B testing is mainly an experiment where two or more page variants are shown to users at random.
- Also, statistical analysis is used to determine which variation works better for a given conversion goal.

## Ring Deplyment [used for ms windows]
- ![](https://learn.microsoft.com/en-us/training/wwl-azure/implement-test-progressive-exposure-deployment/media/rings-0fbd687d.png)
- 
