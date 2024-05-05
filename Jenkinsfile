pipeline {
    agent any
    stages {
        stage('Install dependencies') {
            steps {
                sh 'npm install'
            }
        }
        stage('Build & SonarQube Scanner') {
            steps {
                withSonarQubeEnv('SonarQube_server') {
                    sh 'sonar-scanner'
                }
            }
        }
    }
}
