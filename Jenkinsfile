pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
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
