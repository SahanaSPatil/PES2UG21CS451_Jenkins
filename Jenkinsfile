pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                // Compile the hello.cpp file located inside the main directory
                sh 'g++ -o main/hello main/hello.cpp'
                echo 'Build Stage Successful'
            }
        }
        stage('Test') {
            steps {
                // Intentional error introduced - incorrect command
                sh './main/hello-nonexistent'
                echo 'Test Stage Successful'
            }
        }
        stage('Deploy') {
            steps {
                // Add deployment steps if needed
                echo 'Deployment Successful'
            }
        }
    }
    post {
        failure {
            echo 'Pipeline failed'
        }
    }
}
