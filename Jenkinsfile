pipeline {
    agent any

    stages {

        stage('Build Backend Image') {
            steps {
                sh 'docker build -t app-backend ./backend'
            }
        }

        stage('Build Frontend Image') {
            steps {
                sh 'docker build -t app-frontend ./frontend'
            }
        }

        stage('Deploy Containers') {
            steps {
                sh 'docker stop backend || true'
                sh 'docker stop frontend || true'
                sh 'docker rm backend || true'
                sh 'docker rm frontend || true'

                sh 'docker run -d -p 5000:5000 --name backend app-backend'
                sh 'docker run -d -p 80:80 --name frontend app-frontend'
            }
        }
    }
}
