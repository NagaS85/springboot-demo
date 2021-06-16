pipeline {
    agent {
        docker {
            image 'maven:3.8.1'
            label 'docker'
        }
    }
    options {
        skipStagesAfterUnstable()
    }

    stages {
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }
        stage('Build') {
            steps {
                sh 'mvn  clean package'
            }
        }
    }
}
