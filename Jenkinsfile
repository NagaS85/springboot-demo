pipeline {
    agent {
        label 'docker'
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
