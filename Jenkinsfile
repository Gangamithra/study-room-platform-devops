pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/Gangamithra/study-room-platform-devops.git'
            }
        }

        stage('Build') {
            steps {
                sh 'docker build -t study-room-backend ./server'
            }
        }

        stage('Run') {
            steps {
                sh 'docker run -d -p 5002:5002 study-room-backend || true'
            }
        }
    }
}