### Continuous Integration

  - What is Continuous Integration?
  - Why do we need it?
  - Different phases of adopting Continuous Integration

![IMG](https://github.com/mpruna/CI-CD_with_Jenkins/blob/master/images/what_is_ci.png)

We need to understand continuous integration before we start playing with Jenkins.
Integration is the development practice that requires developers to integrate code into a shared repository several times a day each check and then verified by an automated build teams to detect problems early.
A continuous integration system usually involves a tool that keeps monitoring the version control system. Whenever a change to version control system is detected ,the system would automatically build and test your application. If a built or test is not green, the system immediately notifies the developers to fix the issue right away.

### Why do we need Continuous Integration?
  - Detect problems or bugs, as early as possible, in the
development life cycle.
  - Since the entire code base is integrated, built and tested
constantly , the potential bugs and errors are caught earlier in
the life cycle which results in better quality software.

### Different stages of adopting Continuous Integration

Stage 1.
![IMG](https://github.com/mpruna/CI-CD_with_Jenkins/blob/master/images/ci_stage1.png)

There are no `build servers` at all for the team. The application is built manually on a developer's machine.
The source code is stored in a central repository but is not enforced. The developers need to commit their changes on a regular basis. What happens is that before release a developer or Release Manager would manually integrate the changes during this stage the code changes made by all developers were brought together and forged into a product. This will result in months of conflict changes resolution and potentially would cause release delays.
Stage 2.
![IMG](https://github.com/mpruna/CI-CD_with_Jenkins/blob/master/images/ci_stage2.png)

The team has a built server and automated builds are scheduled on a regular basis typically nightly basis.
This build script would compile the application and runs a set of automated tests. Developers now commit the changes regularly, usually at the end of every day. If a developers commits conflict with another developers work. The build server would alert the team members.

Stage 3.
![IMG](https://github.com/mpruna/CI-CD_with_Jenkins/blob/master/images/ci_stage3.png)

The build server would alert the team members stage 3 The team is now starting to take continuous integration and automated testing to a further step. The server is configured to start a build whenever new code is committed to the central repository.The build process usually involves compiling the application and runs a set of automated unit or integration tests. The build server alerts team members immediately if a bill fails. Broken builds are usually treated as a high priority issue and is fixed quickly.

Stage 4.
![IMG](https://github.com/mpruna/CI-CD_with_Jenkins/blob/master/images/ci_stage4.png)

Stage 4 automated code quality and code coverage metrics are now run along with unit tests to continuously evaluate the code quality.
Gradually the `CI` process gathers useful information about our code base. We will be able to answer questions such as:
  - is the code coverage increasing?
  - Do we have fewer and fewer failures?

This helps teams keep the quality bar of the code base high. We will be notified if good testing practices are slipping.

Stage 5.
![IMG](https://github.com/mpruna/CI-CD_with_Jenkins/blob/master/images/ci_stage5.png)

After successful integration and acceptance tests using automated coding techniques the code is pushed into production.


### Continuous Integration, Continuous Delivery, Continuous Deployment

Terms | Description
-|-
Continuous Integration | The practice of merging development work with the main branch constantly so that the cold is tested as often as possible to catch issues early.
Continuous Delivery | Continual delivery of code to an environment once the code is ready to ship, this could be staging or production ,the idea is the product is delivered to a user base, which can be `QAs` or customers for review and inspection.  Unit tests during continuous integration cannot catch all the bugs in business logic particularly design issues.
Continuous Deployment | The deployment or release of code to production as soon as it is ready, continuous deployment requires continuous integration and continuous delivery.

Read more on [Atlassian](https://www.atlassian.com/continuous-delivery/principles/continuous-integration-vs-delivery-vs-deployment)

### Implementing Continuous integration

![IMG](https://github.com/mpruna/CI-CD_with_Jenkins/blob/master/images/ci_tools.png)


There are several ways to implement `CI`. We can either user Jenkins or Circle CI. [Circle CI](https://github.com/mpruna/Getting_Started_with_CircleCI) is a cloud based `CI` solution.
Continuous Integration requires a shift in the development work flow. A business adopting `CI` must:

  - Fixing broken builds should be treated as a high priority issue for all team
members.
  - The deployment process should be automated, with no manual steps involved.
  - All team members should focus on contributing to high-quality tests because the
confidentiality of the CI process highly depends on the quality of the tests.
  - Each of these steps requires improvements in the practices and engineering culture of continuous integration


### What is Jenkins

   - Jenkins is a continuous integration and build server.
   - It is used to manually, periodically, or automatically build software
development projects.
   - It is an open source Continuous Integration tool written in Java.
   - Jenkins is used by teams of all different sizes, for projects with various
languages.

### Why Jenkins is popular
  - Easy to use
  - Great extensibility:
    – Support different version control systems
    – Code quality metrics
    – Build notifiers
    – UI customization
 
 Jenkins is easy to integrate with a lot of [plug-ins](https://plugins.jenkins.io/)
 such as virtual control systems, code quality metrics, build notifiers, UI customization.
 
 ### Jenkins history
 
 ![IMG](https://github.com/mpruna/CI-CD_with_Jenkins/blob/master/images/jenkins_history.png)
  - Jenkins was originally developed as the Hudson project 
  - Hudson was started in 2004 at Sun by Kohsuke Kawaguchi as a hobby project.
  - First release in 2005.
  - Kohsuke worked on Hudson full time in early 2008.
  - Became the leading Continuous Integration solution with a market share of over 70% in
2010.
  - Renamed to Jenkins in 2011.
  
### Jenkins installation

Jenkins it's an application writen in java. At the current time the latest version supported in java 8.
Before we install jenkins we must install `java 8` available at this [link](https://www.oracle.com/technetwork/java/javase/downloads/jre8-downloads-2133155.html).
Click accept on the `Accept License Agreement` thick box, download and install.

Now install Jenkins. Jenkins installation is available [here](https://jenkins.io/download/), for `Linux`, `Windows` and `Mac`.
After the installation we will have a login prompt, and we have to define the administration for this setup.

![IMG](https://github.com/mpruna/CI-CD_with_Jenkins/blob/master/images/1st_login.png)

Text Direction: Install Java
Section 1, Lecture 9
Configure Java_Home on Windows:

    Right click My Computer and select Properties.
    On the Advanced tab, select Environment Variables, and then edit JAVA_HOME to point to where the JDK software is located, for example, C:\Program Files\Java\jdk1.6.0_02

Configure Java_Home on Linux:

    Login to your account and open the startup script file which is usually ~/.bash_profile  file (or can be .bashrc depending on your envrionment settings)

$ vi ~/.bash_profile

In the startup script, set JAVA_HOME  and PATH 

C shell:

    setenv JAVA_HOME jdk-install-dir
    setenv PATH $JAVA_HOME/bin:$PATH
    export PATH=$JAVA_HOME/bin:$PATH

jdk-install-dir  is the JDK installation director, which should be something similar to /usr/java/jdk1.5.0_07/bin/java

Bourne shell:

    JAVA_HOME=jdk-install-dir
    export JAVA_HOME
    PATH=$JAVA_HOME/bin:$PATH
    export PATH

Korn and bash shells:

    export JAVA_HOME=jdk-install-dir
    export PATH=$JAVA_HOME/bin:$PATH

Type the following command to activate the new path settings immediately:

$ source ~/.bash_profile 

Verify new settings:
$ echo $JAVA_HOME

$ echo $PATH

### Jenkins architecture

![IMG](https://github.com/mpruna/CI-CD_with_Jenkins/blob/master/images/master_slave.png)

Jenkins uses a master and slave architecture to manage distributed builds. A masters job is to handle/schedule build jobs.
A slave is a small Java program that listens for requests from the Jenkins master.
The job of the slaves is to do as they are told, which is mainly executing build jobs dispatched by the master.

Master:

  - Schedule build jobs.
  - Dispatch builds to the slaves for the
actual job execution.
  - Monitor the slaves and record the
build results.
  -  Can also execute build jobs directly.

Slave:
  - Execute build jobs dispatched by
the master

### Jenkins key terms

Term | Description
-|-
Job / Project | Those two terms are used interchangeably. They all refer
to runnable tasks that are controlled / monitored by Jenkins.

Slave / Node:
 - Slaves are computers that are set up to build projects for a master.
 - Jenkins runs a separate program called "slave agent" on slaves.
 - When slaves are registered to a master, a master starts distributing loads to slaves.
 - Node is used to refer to all machines that are part of Jenkins grid, slaves and master.
 
 Executor:
  - Executor is a separate stream of builds to be run on a node in
parallel.
  - A Node can have one or more executors
  
 Build:
  - A build is a result of one of the projects
  
 Plugin:
  - A Plugin, like plugins on any other system, is a piece of software
that extends the core functionality of the core Jenkins server  
=======
### Jenkins Dashboards and Menus

![IMG](https://github.com/mpruna/CI-CD_with_Jenkins/blob/master/images/jenkins_dashboard.png)

 - Main section on the page is the jobs page, but since this is a new installation there will be no listed jobs.
 - New Iterm helps us to create a job/project
 - People manages user/roles rights
 - Build history. Shows a history of the builds on this node. It shows builds that where executed on the master node as well as the slaves
 - My views is where we can setup View filters so setup private view for group of users with different rights.
 - Credentials responsible for managing the global Jenkins credentials
 - Build queue shows build status
 - Build Executor section displays the current build executors on this Jenkins instance
 - Manage Jenkins. Within this section we manage this Jenkins instance:
 
 ![IMG](https://github.com/mpruna/CI-CD_with_Jenkins/blob/master/images/manage_jenkins.png)
 
 - Configure System setups global config such as path to Maven and Java 
 - Configure Global Security, this item comfigures who can edit and view Jenkins through this Web Console
 - Manage Plugins can add, remove, disable or enable plugins that can extend the functionality of Jenkins.
 - System Information/System logs useful for troubleshooting


### Jenkins first job

Click `Create new Job`, give the project a name,and bare in mind that this will be used for the project `build url`, so try to avoid `spaces`.
Jenkins is really versatile, can be used to perform lots of different build jobs such as continuous
integration, nightly builds, perform some repetitive batch tasks, etc.
Freestyle build jobs are general-purpose build jobs, which provides a maximum of flexibility so that you can tailor it to your needs.
Add a project description. The project description will go on the project home page. It provides an overview of the build job's goals and context. 

![IMG](https://github.com/mpruna/CI-CD_with_Jenkins/blob/master/images/first_build_job.png)

We can disable old builds. Build jobs can consume a lot of disk space, especially if you store the build artifacts.
Even without artifacts, keeping a record of every build job consumes additional disk space and memory.
The `Discard Old Builds` option lets you limit the number of builds you record in the build history.
You can either tell Jenkins to only keep recent builds or to keep no more than a specified number of builds.
You also have the option to disable the build. A disabled build will not be executed until you enable it again.
Using this option when you create a new build job is quite rare. But this option is very handy if you want to temporarily suspend a build during
maintenance work or major refactoring.

### Source Control Management section

![IMG](https://github.com/mpruna/CI-CD_with_Jenkins/blob/master/images/source_control_management.png)

Defines the source of the code which will be built by our job.
Jenkins supports CVS and SVN out of box. For the first job we will use the defaults.

### Build triggers

![IMG](https://github.com/mpruna/CI-CD_with_Jenkins/blob/master/images/build_triggers.png)

We can define multiple triggers for this job. If we don't specify any triggers, the job can only be triggered manually. 
In our first job, we will trigger this job manually.

### Build Job

![IMG](https://github.com/mpruna/CI-CD_with_Jenkins/blob/master/images/build_job.png)

Builds steps are the basic building blocks for the Jenkins free style builds process.
Builds steps tell Jenkins exactly, how we want our build project. We can define as many steps as we want within a job.
Here we click add build step. Then we select execute shell. 


### First Job on landing page

![IMG](https://github.com/mpruna/CI-CD_with_Jenkins/blob/master/images/first_job_landing_page.png)


### Setting up a Maven based jenkins job

We need to install the github plug-in. We do this by activating the plug-in in the **manage Jenkins/manage plug-in** section and select the github plug in.

Setting-up a Maven based jobs consists of:
* check out source code from Github
* compile the code
* run the tests
* package the application

[Windows instalation](https://dev-pages.info/how-to-install-maven-on-windows-10/)

In [Maven](https://maven.apache.org/guides/introduction/introduction-to-repositories.html) terminology there are two types of repositories local and remote.
Maven repository keeps your project's all dependencies (library jars, plugin jars etc.). When you run a Maven build, then Maven automatically downloads all the dependency jars into the local repository.
An artifact is one of many kinds of tangible by-products produced during the development of software. Some artifacts help describe the function, architecture, and design of software. 

### Verify installation:

```
mvn -v
c:\
Picked up _JAVA_OPTIONS: -Djava.net.preferIPv4Stack=true
Apache Maven 3.6.1 (d66c9c0b3152b2e69ee9bac180bb8fcc8e6af555; 2019-04-04T22:00:29+03:00)
Maven home: C:\apache-maven-3.6.1\bin\..
Java version: 1.8.0_201, vendor: Oracle Corporation, runtime: C:\Program Files\Java\jre1.8.0_201
Default locale: en_US, platform encoding: Cp1250
OS name: "windows 10", version: "10.0", arch: "amd64", family: "windows"
```

### Maven pom.xml file

POM stands for "Project Object Model". A project contains configuration files, as well as the developers involved and the roles they play, the defect tracking system, the organization and licenses, the URL of where the project lives, the project's dependencies, and all of the other little pieces that come into play to give code life.

* Describe the software project being built, including
    * The dependencies on other external modules.
    * The directory structures.
    * The required plugins.
    * The predefined targets for performing certain tasks such as
compilation and packaging.

Maven project creation:

1. Click **new item**
2. Name the project (**maven-project**)
3. Select **Freestyle project**:

    a. Give a description
    
    b. Under **Source Code Management** check git and supply the [repository URL](https://github.com/jleetutorial/maven-project)
    
    c. Branch specifier leave it at master
    
    d. Create a **Maven target** under build steps and **clean package** under Goals
    
Maven Build Phases
* These lifecycle phases are executed sequentially to complete the default
lifecycle.
* We want to specify the maven package command, this command would
execute each default life cycle phase in order including validate, compile,
test before executing package.
* We only need to call the last build phase to be executed.    


### Maven project execution

Clicking **Build Now** will invoke the project execution. Execution steps can be seen in the console log.
The build steps will be executed sequentially.

1. Project workspace is created, then checkout source code from **Github**

![IMG](../images/workspace_gitfetch.png)

2. Build order determined

![IMG](../images/build_steps.png)

3. For root directory a cleanup is done to remove artifacts from previous projects

![IMG](../images/remove_artifacts.png)

4. For server module execute **clean/compile/test/test results**

![IMG](../images/build_maven.png)
![IMG](../images/server_testres.png)

5. Build *.jar file for server component

![IMG](../images/jarfile.png)

6. Same goes for **webapp**

7. Final **Build Status**

![IMG](../images/build_status.png)


### Different Phases in Maven Build Lifecycle

Phase | Description 
---|---
validate | Validate the project is correct and all necessary information is available.
compile | Compile the source code of the project.
test | Test the compiled source code using a suitable unit testing framework.
package | Take the compiled code and package it in its distributable format.
verify | Run any checks on results of integration tests to ensure quality criteria are met.
install | Install the package into the local repository, for use as a dependency in other projects locally.
deploy | Copy the final package to the remote repository for sharing with other developers and projects.


Jar files in Java. A JAR (Java Archive) is a package file format typically used to aggregate many Java class files and associated metadata and resources (text, images, etc.) into one file to distribute application software or libraries on the Java platform.

In software engineering, a WAR file (Web Application Resource or Web application ARchive) is a file used to distribute a collection of JAR-files, JavaServer Pages, Java Servlets, Java classes, XML files, tag libraries, static web pages (HTML and related files) and other resources that together constitute a web.

### Setting up a GIT trigger

Jenkins can also be used to trigger a build job when something new is committed to a central repository.
We need to specify this in the build triggers: **POLL SCM**
Scheduling is done based on **cron** format

In Cron, each line consists of 5 fields separated by TAB or whitespace.

![IMG](../images/cron_schedule.png)

### Cron Syntax
To specify multiple values for one field:

 (*) all valid values
 
 M-N a range of values

 A,B,Z enumerates multiple values


[SSH Key](https://help.github.com/en/enterprise/2.16/user/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent) must be generated for Jenkins access

To simulate this scenario we fork the original repository. This is the out clone repo:

https://github.com/mpruna/maven-project


Generate an empty commit and a push:

```buildoutcfg
$ git commit --allow-empty
[master b4d8c0b] Allow empty commit to Trigger Jenkins
$ git push
Enumerating objects: 1, done.
Counting objects: 100% (1/1), done.
Writing objects: 100% (1/1), 207 bytes | 207.00 KiB/s, done.
Total 1 (delta 0), reused 0 (delta 0)
To https://github.com/mpruna/maven-project.git
   66ec4ca..b4d8c0b  master -> master
```

Jenkins build trigger based on commit:

```buildoutcfg
Polling Log
View as plain text

This page captures the polling log that triggered this build.

Started on May 5, 2019 3:04:00 PM
Using strategy: Default
using credential 525669c2-ff76-4835-915a-f0ed07537c0c
 > git.exe --version # timeout=10
using GIT_SSH to set credentials Jenkins Git ssh key
 > git.exe ls-remote -h https://github.com/mpruna/maven-project.git # timeout=10
Found 5 remote heads on https://github.com/mpruna/maven-project.git
[poll] Latest remote head revision on refs/heads/master is: b4d8c0b7f38f714c511b6c7f404ef99c161563eb
Done. Took 3.4 sec
Changes found
```

 


References:

 https://en.wikipedia.org/wiki/Artifact_(software_development)
  
 https://softwareengineering.stackexchange.com/questions/106473/what-does-artifact-mean#106474
  
 https://maven.apache.org/pom.html
 
 https://en.wikipedia.org/wiki/WAR_(file_format)
 
 
 