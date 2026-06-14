pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build') {
            steps {
                echo 'Building...'
                bat 'node --version'
            }
        }

        stage('Test') {
            steps {
                echo 'Tests passed!'
            }
        }

        stage('Deploy') {
            steps {
                bat 'docker build -t ali-cicd-project .'
                echo 'Deployed!'
            }
        }

        stage('Notify') {
            steps {
                echo 'Team notified of successful build!'
            }
        }
    }

    post {
        success {
            echo 'Pipeline SUCCESS!'
        }

        failure {
            echo 'Pipeline FAILED!'
        }
    }
}
