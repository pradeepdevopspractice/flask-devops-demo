pipeline {

    agent any

    environment {
        KUBECONFIG = 'C:\Users\prade\.kube\config'
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

        stage('check Kubernetes') {
            steps {
                bat 'kubectl config current-context'
                bat 'kubectl get nodes'
            }
        }
    }
}