pipeline {

    agent any

    environment {

        IMAGE = "YOUR_DOCKERHUB_USERNAME/abc-bank-demo"

    }

    stages {

        stage('Clone') {

            steps {

                checkout scm

            }

        }

        stage('Docker Build') {

            steps {

                sh 'docker build -t $IMAGE:latest .'

            }

        }

        stage('Docker Push') {

            steps {

                sh 'docker push $IMAGE:latest'

            }

        }

        stage('Deploy') {

            steps {

                sh '''
                docker pull $IMAGE:latest

                docker stop abc-bank-demo || true

                docker rm abc-bank-demo || true

                docker run -d --name abc-bank-demo -p 80:80 $IMAGE:latest
                '''
            }

        }

    }

}