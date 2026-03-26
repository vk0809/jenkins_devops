pipeline {

    agent any

    stages {

        stage('Clone Code') {
            steps {
                git 'https://github.com/vk0809/jenkins_devops.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t myapp:latest .'
            }
        }

        stage('Deploy to Kubernetes') {
            steps {
                sh 'kubectl apply -f deployment.yml'
                sh 'kubectl apply -f service.yml'
            }
        }
    }
}
