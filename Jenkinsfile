pipeline {

    agent any

    environment {
        IMAGE_NAME = "leader67/bank-app"
        TAG = "v1"
    }

    stages {

        // Stage 1: Clone source code from GitHub
        stage('Clone Repository') {
            steps {
                echo "Cloning GitHub Repository..."

                git branch: 'main',
                    url: 'https://github.com/sreerammaddala/Bank-Demo.git'
            }
        }

        // Stage 2: Verify repository files
        stage('Verify Files') {
            steps {
                echo "Verifying downloaded files..."

                sh 'pwd'
                sh 'ls -la'
                sh 'find . -maxdepth 2'
            }
        }

        // Stage 3: Build Docker Image
        stage('Build Docker Image') {
            steps {
                echo "Building Docker Image..."

                sh 'docker build -t ${IMAGE_NAME}:${TAG} .'
            }
        }

        // Stage 4: Push Image to Docker Hub
        stage('Push Docker Image') {
            steps {
                echo "Pushing Docker Image..."

                sh 'docker push ${IMAGE_NAME}:${TAG}'
            }
        }

        // Stage 5: Pull Latest Image
        stage('Pull Latest Image') {
            steps {
                echo "Pulling Latest Docker Image..."

                sh 'docker pull ${IMAGE_NAME}:${TAG}'
            }
        }

        // Stage 6: Deploy Docker Container
        stage('Deploy Container') {
            steps {
                echo "Deploying Docker Container..."

                sh '''
                docker stop bank-app || true
                docker rm bank-app || true

                docker run -d \
                  --name bank-app \
                  -p 80:80 \
                  ${IMAGE_NAME}:${TAG}
                '''
            }
        }
    }

    post {

        success {
            echo "Application Successfully Deployed."
        }

        failure {
            echo "Pipeline Failed."
        }
    }
}
