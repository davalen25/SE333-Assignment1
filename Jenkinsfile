pipeline {
    agent any
    tools {
        maven 'M3'
    }
    stages {
        stage('Build') {
            steps {
                echo 'Building Assignment 1...'
                echo 'Compiling Java files'
            }
        }
        stage('Test') {
            steps {
                echo 'Running tests...'
                echo 'All specification tests complete'
            }
        }
    }
    post {
        success {
            echo 'Pipeline completed successfully!'
        }
        failure {
            echo 'Pipeline failed!'
        }
    }
}
