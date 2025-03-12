pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                script {
                    sh 'g++ main.cpp -o PES1UG22AM019-1'
                }
            }
        }
        stage('Test') {
            steps {
                script {
                    sh 'chmod +x PES1UG22AM019-1'
                    sh './PES1UG22AM019-1'
                }
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying application...'
            }
        }
    }

    post {
        failure {
            echo 'Pipeline failed'
        }
    }
}
