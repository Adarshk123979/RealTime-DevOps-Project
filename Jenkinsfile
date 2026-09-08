pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                echo 'Source code checked out successfully.'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'sudo docker build -t flask-app:v1 .'
            }
        }

        stage('Remove Old Container') {
            steps {
                sh 'sudo docker rm -f flask-container || true'
            }
        }

        stage('Run Container') {
            steps {
                sh 'sudo docker run -d -p 5000:5000 --name flask-container flask-app:v1'
            }
        }
    }
}
