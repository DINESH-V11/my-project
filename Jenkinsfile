pipeline {
    agent any

    triggers {
        githubPush()
    }

    stages {

        stage('Checkout') {
            steps {
                echo 'Checking out code from GitHub'
                checkout scm
            }
        }

        stage('Verify Files') {
            steps {
                echo 'Listing project files'
                bat 'dir'
            }
        }

        stage('Build (HTML Project)') {
            steps {
                echo 'No build needed for static HTML project'
            }
        }

        stage('Test') {
            steps {
                echo 'Basic test: checking index.html'
                bat 'if exist index.html (echo index.html found) else (exit 1)'
            }
        }
    }

    post {
        success {
            echo 'Pipeline completed successfully'
        }
        failure {
            echo 'Pipeline failed'
        }
    }
}
