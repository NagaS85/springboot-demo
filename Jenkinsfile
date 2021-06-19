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
	stage('Checkout external proj') {
		steps {
		    git branch: 'master',
			credentialsId: 'GIT_AUTH',
			url: 'https://github.com/NagaS85/springboot-demo.git/'

		    
		}
    }

        /*stage('Build') {
		steps {
		withMaven{
		  bat "mvn clean package"
		} // withMaven will discover the generated Maven artifacts, JUnit Surefire & FailSafe reports and FindBugs reports
           }
			
        }
	stage('DEPLOY') {
		steps {
		withMaven{
		  bat "mvn spring-boot:run"
		} // withMaven will discover the generated Maven artifacts, JUnit Surefire & FailSafe reports and FindBugs reports
           }
			
        }  */  
}
}
