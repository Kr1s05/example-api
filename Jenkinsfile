pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                // Checkout the source code from the repository
                git 'https://github.com/Kr1s05/example-api.git'
                
                // Build the Go project
                sh 'go build'
            }
            post {
                success {
                    // Archive the build artifacts
                    archiveArtifacts artifacts: '**/example-api'
                }
            }
        }
        
        stage('Test') {
            steps {
                // Run tests for the Go project
                sh 'go test ./...'
            }
        }
        
        stage('Deploy') {
            steps {
               sh 'exmple-api'
            }
        }
    }
    
    // Define post actions for the entire pipeline
    post {
        always {
            // Cleanup steps, if necessary
        }
    }
}