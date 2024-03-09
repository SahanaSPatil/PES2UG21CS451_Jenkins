pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                script {
                    // Compile the .cpp file using shell script
                    build 'PES2UG21CS451-1'
                    sh 'g++ main.cpp -o output'
                }
            }
        }
        stage('Test') {
            steps {
                script {
                    // Print output of the .cpp file using shell script
                    sh './output'
                }
            }
        }
        stage('Deploy') {
            steps {
                // Add steps to deploy the application (if any)
                // This stage is just a placeholder
                echo 'Deploying application...'
            }
        }
    }
    
    post {
        always {
            // Display 'pipeline failed' in case of any errors within the pipeline
            catchError(buildResult: 'FAILURE', stageResult: 'FAILURE') {
                echo 'Pipeline completed successfully'
            }
        }
    }
}

