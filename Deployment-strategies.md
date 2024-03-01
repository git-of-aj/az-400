## BG
- Blue-green deployment is a technique that reduces risk and downtime by running two identical environments called `blue and green`.
- blue is currently live, and green is idle.
- eployment and final testing stage occur in an environment that isn't live: in this example, green. Once you've deployed and thoroughly tested the software in green, switch the router or load balancer so all incoming requests go to green instead of blue.
-  it involves database schema changes, this process isn't straightforward. You probably can't swap your application
