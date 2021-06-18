pipeline {
    agent any
    
    options {
        skipStagesAfterUnstable()
    }

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }
        stage('Example') {
            steps {
                echo "Running ${env.BUILD_ID} on ${env.JENKINS_URL}"
            }
        }

        stage('Build') {
		steps {
		withMaven{
		  sh "mvn clean verify"
		} // withMaven will discover the generated Maven artifacts, JUnit Surefire & FailSafe reports and FindBugs reports
           }
			
        }
}
}
