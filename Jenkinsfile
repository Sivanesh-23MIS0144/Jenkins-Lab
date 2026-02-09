pipeline {
    agent any
    stages {
        stage('1. Git Commit & Pull') {
            steps {
                echo 'Triggered by Git Commit...'
                checkout scm // Automatically pulls the latest code
            }
        }
        stage('2. Compile Code') {
            steps {
                echo 'Compiling Java Source...'
                // This will fail if there is a syntax error in your Java file
                sh 'javac *.java'
            }
        }
        stage('3. Run Tests') {
            steps {
                echo 'Running Unit Tests...'
                sh 'java Hello'
            }
        }
    }
    post {
        success {
            echo 'Archiving Successful Build...'
            archiveArtifacts artifacts: '*.class', fingerprint: true // Task 15.3: Archive artifacts
        }
        failure {
            echo 'CI Flow Failed! Please fix the code errors.' // Task 15.4: Fail build on error
        }
    }
}
