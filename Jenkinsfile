pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build Docker Images') {
            steps {
                sh 'docker build -t bezkoder-api ./bezkoder-api'
                sh 'docker build -t bezkoder-ui ./bezkoder-ui'
            }
        }

        stage('Deploy') {
            steps {
                sh 'docker-compose up -d'
            }
        }

    }
}
