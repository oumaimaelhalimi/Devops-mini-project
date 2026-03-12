pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/oumaimaelhalimi/project.git'
            }
        }
        stage('Build Docker Images') {
            steps {
                sh 'docker-compose build'
            }
        }
        stage('Run Tests') {
            steps {
                sh 'docker-compose run backend npm test'
            }
        }
        stage('Deploy') {
            steps {
                sh 'docker-compose up -d'
            }
        }
    }
}
