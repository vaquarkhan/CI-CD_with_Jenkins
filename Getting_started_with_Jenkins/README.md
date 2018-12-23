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

Stag 2.
![IMG](https://github.com/mpruna/CI-CD_with_Jenkins/blob/master/images/ci_stage2.png)

The team has a built server and automated builds are scheduled on a regular basis typically nightly basis.
This build script would compile the application and runs a set of automated tests. Developers now commit the changes regularly, usually at the end of every day. If a developers commits conflict with another developers work. The build server would alert the team members.
