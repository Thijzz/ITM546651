pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Install Dependencies') {
            steps {
                dir('frontend') {
                    bat 'npm install'
                }
            }
        }

        stage('Security Test') {
            steps {
                dir('frontend') {
                    echo 'Running security tests...'
                    bat 'npm audit --audit-level=high'
                }
            }
        }

        stage('Build') {
            steps {
                echo 'Building the project...'
                // Voeg hier je frontend build commando toe
                dir('frontend') {
                    bat 'dotnet build' // voorbeeld voor .NET frontend
                }
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
                dir('frontend') {
                    bat 'dotnet test' // als je unit tests hebt
                }
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