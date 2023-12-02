pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        

        stage('Build Docker Image') {
            steps {
                script {
                    // Build Docker image
                    sh 'docker build -t my-petclinic-app .'
                }
            }
        }

        

        stage('Deploy') {
            steps {
                script {
                    // Deploy Docker image (replace with your deployment command)
                    sh 'docker-compose up -d'
                }
            }
        }
    }
}
