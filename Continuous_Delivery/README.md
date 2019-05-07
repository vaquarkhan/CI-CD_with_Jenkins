### Archive artifacts

A typical Jenkins workflow would be to package the software file post build and deploy it in a staging environment.

![IMG](../images/continuous_delivery.png) 

We can simulate this by action by invoking archive action in the post build section of the job.
Next we trigger a build manually.

![IMG](../images/archive_war.png)

In a real world scenario we might have build jobs that incorporate many steps.
It can be hard to follow along these steps. We can use a build pipeline plug in which can help us define a better view of the build process.

![IMG](../images/build_pipeline.png)

The most inportant step is to define the initial build step.

![IMG](../images/pipeline_initial_job.png)
![IMG](../images/run_build.png)


To optimise the build pipeline we might execute some jobs in parallel to improve time.
In our case we can remove the checkstyle from the initial build step and set it up as a independent build.

![IMG](../images/parellel_pipeline.png) 
![IMG](../images/parellel_pipeline_exec.png)


