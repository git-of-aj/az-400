## BG
- Blue-green deployment is a technique that reduces risk and downtime by running two identical environments called `blue and green`.
- blue is currently live, and green is idle.
- eployment and final testing stage occur in an environment that isn't live: in this example, green. Once you've deployed and thoroughly tested the software in green, switch the router or load balancer so all incoming requests go to green instead of blue.
-  it involves database schema changes, this process isn't straightforward. You probably can't swap your application

## Canaries =
You have a group of users who are better at dealing with new code and issues if they arise, and these people are often called Canaries.
- A canary release is a way to identify potential problems without exposing all your end users to the issue at once.
- Canary releases can be implemented using a combination of feature toggles, traffic routing, and deployment slots.
1. You can route a percentage of traffic to a deployment slot with the new feature enabled.
2. You can target a specific user segment by using feature toggles.
- [feature flag](https://learn.microsoft.com/en-us/azure/azure-app-configuration/manage-feature-flags)

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
