pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo 'Pulling code from GitHub...'
                // Jenkins automatically performs checkout when using 'Pipeline script from SCM'
            }
        }

        stage('Build') {
            steps {
                echo 'Compiling the application...'
                // Using the Java compilation command from Task 7
                sh '''
                    echo "public class Hello { public static void main(String[] args) { System.out.println(\\"Build Successful\\"); } }" > Hello.java
                    javac Hello.java
                '''
            }
        }

        stage('Test') {
            steps {
                echo 'Running unit tests...'
                // Verifying the build as practiced in Task 10
                sh 'java Hello'
            }
        }
    }

    /* Task 12: Post-Build Actions */
    post {
        success {
            echo 'Build Successful! Lab cycle complete.'
        }
        failure {
            echo 'Build Failed! Please check the logs.'
        }
        always {
            echo 'Cleaning up the workspace...'
        }
    }
}
