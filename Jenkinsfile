pipeline {

    agent any

    environment {

        IMAGE_NAME = "sushmamounika/bank-app"

        TAG = "v1"

    }

    stages {

        stage('Clone Repository') {

            steps {

                echo "Cloning GitHub Repository..."

                checkout scm

            }

        }

        stage('Verify Files') {

            steps {

                sh 'pwd'

                sh 'ls -la'

            }

        }

        stage('Build Docker Image') {

            steps {

                echo "Building Docker Image..."

                sh 'docker build -t ${IMAGE_NAME}:${TAG} .'

            }

        }

        stage('Push Docker Image') {

            steps {

                echo "Pushing Image to Docker Hub..."

                sh 'docker push ${IMAGE_NAME}:${TAG}'

            }

        }

        stage('Pull Latest Image') {

            steps {

                echo "Pulling Latest Image..."

                sh 'docker pull ${IMAGE_NAME}:${TAG}'

            }

        }

        stage('Deploy Container') {

            steps {

                echo "Deploying Container..."

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
