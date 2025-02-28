pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                git branch: 'main', url: "https://github.com/NoorulAyaan/New-Test-Demo-App.git"
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t my-docker-image .'
            }
        }

        stage('Push to Docker Hub') {
            steps {
                withDockerRegistry([credentialsId: 'docker-hub-credentials', url: '']) {
                    sh 'docker push my-docker-image'
                }
            }
        }
    }
}
