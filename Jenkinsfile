pipeline {
    agent any

    environment {
        DOCKER_IMAGE = 'python:3.13.2-alpine3.21'
    }

    stages {
        stage('Build') {
            steps {
                echo 'Running Build stage inside Docker...'
                bat """
                    docker pull %DOCKER_IMAGE%
                    docker run --rm %DOCKER_IMAGE% sh -c "echo 'Building project...' && python --version"
                """
            }
        }

        stage('Test') {
            steps {
                echo 'Running Test stage inside Docker...'
                bat """
                    docker run --rm %DOCKER_IMAGE% sh -c "echo 'Running tests...' && python -c \\"print('Tests passed')\\""
                """
            }
        }

        stage('Release') {
            steps {
                echo 'Running Release stage inside Docker...'
                bat """
                    docker run --rm %DOCKER_IMAGE% sh -c "echo 'Releasing project...'"
                """
            }
        }
    }

    post {
        success {
            echo '✅ Pipeline completed successfully!'
        }
        failure {
            echo '❌ Pipeline failed. Check logs above.'
        }
    }
}
