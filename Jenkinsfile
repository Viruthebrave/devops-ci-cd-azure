pipeline {
    agent any

    stages {
        stage('Build Docker Image') {
            steps {
                bat 'docker build -t devops-flask-app:latest .'
            }
        }

        stage('Run Docker Container') {
            steps {
                bat '''
                docker stop devops_container 2>nul || exit 0
                docker rm devops_container 2>nul || exit 0
                docker run -d -p 5000:5000 --name devops_container devops-flask-app:latest
                '''
            }
        }
    }
}
