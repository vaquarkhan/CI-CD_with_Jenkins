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
The source code is stored in a central repository but is not enforced. The developers need to commit their changes on a regular basis. What happens is that before release a developer or Release Manager would mentally integrate the changes during this stage the code changes made by all developers were brought together and forged into a product. This will result in months of conflict changes resolution and potentially would cause release delays.

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


### Difference between Continuous Integration, Continuous Delivery and Continuous Deployment

Terms | Description
-|-
Continuous Integration | The practice of merging development work with the main branch constantly so that the cold is tested as often as possible to catch issues early.
Continuous Delivery | Continual delivery of code to an environment once the code is ready to
ship, this could be staging or production ,the idea is the product is delivered to a user base, which can be `QAs` or customers for review and inspection.  Unit tests during continuous integration cannot catch all the bugs in business logic particularly design issues.
Continuous Deployment | The deployment or release of code to production as soon as it is ready, continuous deployment requires continuous integration and continuous delivery.

### Implementing Continuous integration

![IMG](https://github.com/mpruna/CI-CD_with_Jenkins/blob/master/images/ci_tools.png)

There are several ways to implement `CI`. We can either user Jenkins or Circle CI.[Circle CI](https://github.com/mpruna/Getting_Started_with_CircleCI) is a cloud based `CI` solution.

Continuous Integration requires a shift in the development work flow. A business adopting `CI` must:

  - Fixing broken builds should be treated as a high priority issue for all team
members.
  - The deployment process should be automated, with no manual steps involved.
  - All team members should focus on contributing to high-quality tests because the
confidentiality of the CI process highly depends on the quality of the tests.
  - Each of these steps requires improvements in the practices and engineering culture of continuous integration
