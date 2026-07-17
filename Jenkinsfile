pipeline {

    agent any

    environment {
        IMAGE_NAME = "flask-demo"
        IMAGE_TAG = "latest"
    }

    stages {

        stage('Clone Repository') {
            steps {
                git branch: 'main',
                url: 'https://github.com/pradeepdevopspractice/flask-devops-demo.git'
            }
        }

        stage('Build Docker Image') {
            steps{
                bat 'docker build -t flask-demo:latest .'
            }
        }

        stage('Deploy to Kubernetes') {
            steps {
                bat 'kubectl apply -f deployment.yaml'
                bat 'kubectl apply -f service.yaml'
            }
        }
    }
}