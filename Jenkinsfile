pipeline {
    agent any
    
    stages {
        stage('Clone Repository') {
            steps {
                checkout([
                    $class: 'GitSCM', 
                    branches: [[name: '*/main']], 
                    userRemoteConfigs: [[url: 'https://github.com/akdino/PES1UG22AM019_Jenkins.git']]
                ])
            }
        }
        
        stage('Build') {
            steps {
                script {
                    build 'PES1UG22AM019-1'
                    sh 'g++ new.cpp -o output'
                }
            }
        }
        
        stage('Test') {
            steps {
                script {
                    sh './output'
                }
            }
        }
        
        stage('Deploy') {
            steps {
                script {
                    echo "Deploying..."
                }
            }
        }
    }
    
    post {
        success {
            echo 'Build and Deployment Successful!'
        }
        failure {
            echo 'Build Failed.'
        }
        always {
            echo 'Cleaning up...'
        }
    }
}
