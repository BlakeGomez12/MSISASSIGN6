pipeline {
    agent any

    stages {
        stage('Run in Docker') {
            steps {
                bat 'docker run --rm python:3.13.2-alpine3.21 python --version'
            }
        }
    }
}
