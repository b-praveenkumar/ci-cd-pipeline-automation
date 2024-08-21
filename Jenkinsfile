pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                script {
                    docker.build('flask-app')
                }
            }
        }
        stage('Test') {
            steps {
                script {
                    docker.image('flask-app').inside {
                        sh 'echo Running tests'
                        sh 'python -m unittest discover -s tests'
                    }
                }
            }
        }
        stage('Lint') {
            steps {
                script {
                    docker.image('flask-app').inside {
                        sh 'echo Running linter'
                        sh 'flake8 .'
                    }
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