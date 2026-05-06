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
                dir('server') {
                    sh 'docker run --rm -v $PWD:/app -w /app node:20 npm install'
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
                sh 'docker run -d -p 5002:5002 study-room-backend'
            }
        }
    }
}