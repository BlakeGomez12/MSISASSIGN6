pipeline {
    agent {
        docker {
            image 'python:3.13.2-alpine3.21'
            args '-u root'  // optional: run as root in container
        }
    }

    stages {
        stage('Build') {
            steps {
                echo 'Running Build Stage inside Docker'
                sh 'python --version'
                sh 'echo "Simulating build..."'
            }
        }

        stage('Test') {
            steps {
                echo 'Running Test Stage inside Docker'
                sh 'echo "Running tests..."'
                // Example: sh 'pytest tests/' or similar
            }
        }

        stage('Release') {
            steps {
                echo 'Running Release Stage inside Docker'
                sh 'echo "Packaging and releasing..."'
                // Example: sh 'python setup.py sdist'
            }
        }
    }

    post {
        success {
            echo '✅ Pipeline completed successfully inside Docker.'
        }
        failure {
            echo '❌ Pipeline failed. Check logs for more info.'
        }
    }
}
