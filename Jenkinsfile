pipeline {
    agent any

    options {
        skipDefaultCheckout(true)   // 👈 VERY IMPORTANT
    }

    stages {
        stage('Clone Code') {
            steps {
                sh 'git clone https://github.com/sunnyajay293/ajay-nginx.git'
            }
        }
    }
}
