pipeline {
    agent any
    
    environment {
        SONAR_TOKEN = credentials('SonarQube')
    }
    
    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/tannuahuja/nodejs-notes-app'
            }
        }
        stage('Install dependencies') {
            steps {
                sh 'npm install'
            }
        }
        stage('SonarQube analysis') {
            steps {
                withSonarQubeEnv('SonarQubeServer') {
                    sh "sonar-scanner -Dsonar.login=${SONAR_TOKEN}"
                }
            }
        }
        // Add more stages as needed (e.g., testing, deployment)
    }
    
    post {
        always {
            // Cleanup or post-processing steps
        }
    }
}
