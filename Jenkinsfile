pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/Viruthebrave/devops-ci-cd-azure.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    docker.build("devops-flask-app:latest")
                }
            }
        }
    }
}
