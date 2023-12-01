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

        stage('Push to Docker Registry') {
            steps {
                script {
                    // Push Docker image to Docker Hub (replace with your registry)
                    sh 'docker tag my-petclinic-app arjunreddytcpl/my-petclinic-app:latest'
                    sh 'docker push arjunreddytcpl/my-petclinic-app:latest'
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
