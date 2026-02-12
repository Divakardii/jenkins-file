pipeline {
    agent any

    stages {

        stage('Clone Code') {
            steps {
                echo 'Cloning handled by Jenkins SCM configuration'
            }
        }

        stage('Build & Deploy') {
            steps {
                sh 'docker-compose down || true'
                sh 'docker-compose up --build -d'
            }
        }
    }
}
