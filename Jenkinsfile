pipeline {
    agent any
    
    options {
        skipStagesAfterUnstable()
    }
parameters {
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')

        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')

        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')

        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')

        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
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
		  bat "mvn clean verify"
		} // withMaven will discover the generated Maven artifacts, JUnit Surefire & FailSafe reports and FindBugs reports
           }
			
        }
	stage('DEPLOY') {
		steps {
		withMaven{
		  bat "java -jar target/demo-0.0.1-SNAPSHOT.jar &"
		} // withMaven will discover the generated Maven artifacts, JUnit Surefire & FailSafe reports and FindBugs reports
           }
			
        }    
}
}
