pipeline {
    agent any
    
    environment {
        DOCKER_COMPOSE_VERSION = '1.29.0' // Set the Docker Compose version you want to use
    }
    
    stages {
        stage('Checkout') {
            steps {
                // Checkout the source code from your version control system (e.g., Git)
                checkout scm
            }
        }
        
        stage('Build and Deploy') {
            steps {
                script {
                    // Install Docker Compose
                    sh "curl -L https://github.com/docker/compose/releases/download/1.29.0/docker-compose-$(uname -s)-$(uname -m) -o /usr/local/bin/docker-compose"
                    sh 'chmod +x /usr/local/bin/docker-compose'
                    
                    // Build and deploy using Docker Compose
                    sh 'docker-compose up -d'
                }
            }
        }
    }
    
    post {
        always {
            // Clean up or perform any final steps
            sh 'docker-compose down' // Stop and remove the containers when the pipeline is finished
        }
    }
}
