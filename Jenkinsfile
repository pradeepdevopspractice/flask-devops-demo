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
                sh 'docker build -t $IMAGE_NAME:$IMAGE_TAG .'
            }
        }

        stage('Deploy to Kubernetes') {
            steps {
                sh 'kubectl apply -f deployment.yaml'
                sh 'kubectl apply -f service.yaml'
            }
        }
    }
}