pipeline {
    agent any

    stages {
        stage ('Security test') {
            steps {
                echo 'Running security tests...'
                bat 'npm audit --audit-level=high'
        }
        stage('Checkout') {
            steps {
                // Code ophalen van de repository
                checkout scm
            }
        }

        stage('Build') {
            steps {
                echo 'Building the project...'
 
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
  
            }
        }
    }

    post {
        success {
            echo 'Pipeline completed successfully!'
        }
        failure {
            echo 'Pipeline failed!'
        }
    }
}
