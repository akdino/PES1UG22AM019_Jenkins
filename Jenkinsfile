pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                script {
                    echo "Building the C++ file..."
                    sh 'g++ -o PES1UG22AM019-1 main/hello.cpp || (echo "Build Failed" && exit 1)'
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    echo "Testing the compiled file..."
                    sh './PES1UG22AM019-1 || (echo "Test Failed" && exit 1)'
                }
            }
        }

        stage('Deploy') {
            steps {
                script {
                    echo "Deploying the application..."
                    sh 'echo "Deployment successful"'
                }
            }
        }
    }
}
