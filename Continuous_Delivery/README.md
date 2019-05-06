### Archive artifacts

A typical Jenkins workflow would be to package the software file post build and deploy it in a staging environment.

![IMG](../images/continuous_delivery.png) 

We can simulate this by action by invoking archive action in the post build section of the job.
Next we trigger a build manually.

![IMG](../images/archive_war.png)