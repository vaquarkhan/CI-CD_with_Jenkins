### Pipeline as a Code

Jenkins Pipeline provides an extensible set of tools for modeling simple-to-complex delivery pipelines "as code". The definition of a Jenkins Pipeline is typically written into a text file (called a Jenkinsfile) which in turn is checked into a project’s source control repository.
Jenkinsfile is a text file that contains the definition of a Jenkins Pipeline and is checked into source control.
 
Example below contains a pipeline with 3 stages

```buildoutcfg
pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}
``` 

### Benefits of a code-based pipeline

* Version control
* Best Practices
* Less error-prone execution of jobs
* Logic-based execution of steps

References:

* https://jenkins.io/doc/pipeline/tour/hello-world/
* https://jenkins.io/doc/book/pipeline/jenkinsfile/

