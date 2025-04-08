pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                bat 'docker run --rm python:3.13.2-alpine3.21 python --version'
            }
        }
    }
    stages {
        stage('Test') {
            steps {
                bat 'docker run --rm python:3.13.2-alpine3.21 python --version'
            }
        }
    }
    stages {
        stage('Release') {
            steps {
                bat 'docker run --rm python:3.13.2-alpine3.21 python --version'
            }
        }
    }
}

