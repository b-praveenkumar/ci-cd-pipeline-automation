pipeline {
    agent any

    stages {
        stage('Build Docker Image') {
            steps {
                script {
                    docker.build('flask-app')
                }
            }
        }

        stage('Login to AWS ECR') {
            steps {
                script {
                    sh 'aws ecr get-login-password --region us-east-1 | docker login --username AWS --password-stdin <your-aws-account-id>.dkr.ecr.us-east-1.amazonaws.com'
                }
            }
        }

        stage('Push Docker Image') {
            steps {
                script {
                    docker.tag('flask-app:latest', '<your-aws-account-id>.dkr.ecr.us-east-1.amazonaws.com/flask-app:latest')
                    docker.push('<your-aws-account-id>.dkr.ecr.us-east-1.amazonaws.com/flask-app:latest')
                }
            }
        }

        stage('Deploy to ECS') {
            steps {
                script {
                    sh 'aws ecs update-service --cluster flask-app-cluster --service flask-app-service --force-new-deployment'
                }
            }
        }
    }
}