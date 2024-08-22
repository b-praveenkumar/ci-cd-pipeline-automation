pipeline {
    agent any

    environment {
        DOCKER_CMD = "/usr/local/bin/docker"
    }

    stages {
        stage('Build') {
            steps {
                script {
                    sh "${DOCKER_CMD} build -t flask-app ."
                }
            }
        }
        stage('Test') {
            steps {
                script {
                    sh "${DOCKER_CMD} inspect -f . flask-app"
                }
            }
        }
        stage('Lint') {
            steps {
                script {
                    sh "${DOCKER_CMD} run flask-app flake8 ."
                }
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying to cloud...'
                // Add deployment script here
            }
        }
    }
}