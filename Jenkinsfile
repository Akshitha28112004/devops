pipeline {
    agent any
    stages {
        stage('Build Docker Image') {
            steps {
                bat 'docker build -t register:v1 .'
            }
        }
        stage('Push to Docker Hub') {
            steps {
                bat 'docker tag register:v1 akshitha28/register:v1'
                bat 'docker push akshitha28/register:v1'
            }
        }
        stage('Deploy to Kubernetes') {
            steps {
                bat 'kubectl apply -f C:/DevOps/week-2/deployment.yaml'
                bat 'kubectl apply -f C:/DevOps/week-2/service.yaml'
            }
        }
        stage('Automated UI Test') {
            steps {
                bat 'python C:/DevOps/week-2/test_registration.py'
            }
        }
    }
}
