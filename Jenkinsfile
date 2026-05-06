pipeline {
    agent any

    stages {

        stage('Install Dependencies') {
            steps {
                dir('server') {
                    sh 'npm install'
                }
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t study-room-backend ./server'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker stop backend || true'
                sh 'docker rm backend || true'
                sh 'docker run -d -p 5002:5002 --name backend study-room-backend'
            }
        }
    }
}