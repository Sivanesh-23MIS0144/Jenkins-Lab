pipeline {
    agent any
    stages {
        stage('Remote Checkout') {
            steps {
                echo 'Jenkins is reading this from GitHub!'
            }
        }
        stage('Lab Verification') {
            steps {
                sh 'java -version'
                echo 'Task 11 is running smoothly.'
            }
        }
    }
}
