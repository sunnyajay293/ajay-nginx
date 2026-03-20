pipeline {
    agent any

    options {
        skipDefaultCheckout(true)
    }

    stages {
        stage('Clone Code') {
            steps {
                sh '''
                rm -rf ajay-nginx
                git clone https://github.com/sunnyajay293/ajay-nginx.git
                '''
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t sunnyajy293/ajay-nginx:latest ajay-nginx'
            }
        }

        stage('Push to DockerHub') {
            steps {
                withCredentials([usernamePassword(
                    credentialsId: 'docker-creds',
                    usernameVariable: 'DOCKER_USER',
                    passwordVariable: 'DOCKER_PASS'
                )]) {
                    sh '''
                    echo $DOCKER_PASS | docker login -u $DOCKER_USER --password-stdin
                    docker push sunnyajy293/ajay-nginx:latest
                    '''
                }
            }
        }
    }
}
