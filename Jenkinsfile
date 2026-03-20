pipeline {
    agent any

    options {
        skipDefaultCheckout(true)
    }

    stages {
        stage('Clone Code') {
            steps {
                sh 'git clone https://github.com/sunnyajay293/ajay-nginx.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t sunnyajy293/ajay-nginx:latest ajay-nginx'
            }
        }
    }
}
