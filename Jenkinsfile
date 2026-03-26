pipeline {

    agent any 

    stages {

        steps('Clone code') {
            steps {
                git 'https://github.com/vk0809/jenkins_devops.git'
            }

        }

        stages('Build Docker Image') {

            steps {
                sh 'docker build -t myapp:latest .'
            }
        }
    
        stages('Deploy to Kubernetes') {

            steps {
                sh 'kubectl apply -f deployment.yml'
                sh 'kubectl apply -f service.yml'
            }
        }
    }
}

