pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                checkout scm
                sh 'ls -l main'  // Lists files in the 'main' directory to debug
            }
        }
        stage('Build') {
            steps {
                sh 'g++ main/hello.cpp -o main/hello_exec'
            }
        }
        stage('Test') {
            steps {
                sh './main/hello_exec'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deployment Successful'
            }
        }
    }
    post {
        failure {
            echo 'Pipeline Failed'
        }
    }
}
