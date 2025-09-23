pipeline {
    agent any
    stages {
        stage('Build Docker Image') {
            steps {
                bat 'docker build -t registration:v1 .'
            }
        }
        stage('Push to Docker Hub') {
            steps {
                bat 'docker tag registration:v1 sriludone/registration:v1'
                bat 'docker push sriludone/registration:v1'
            }
        }
        stage('Deploy to Kubernetes') {
            steps {
                bat "C:\DeVops\week12\deployment.yaml"
                bat "C:\DeVops\week12\service.yaml"
            }
        }
    }
}
