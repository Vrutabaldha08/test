pipeline {
    agent any
    
    environment {
        // Define a variable to store the branch name
        branchName = "${env.BRANCH_NAME}"
    }
    
    stages {
        stage('Build') {
            when {
                expression { branchName in ['b1', 'b2', 'b3'] }
            }
            steps {
                script {
                    // Only execute build steps if the branch matches the stage
                    echo "Building for ${branchName}..."
                    // Your build steps for the branch
                }
            }
        }
        
        stage('Test') {
            when {
                expression { branchName in ['b1', 'b2', 'b3'] }
            }
            steps {
                script {
                    // Only execute test steps if the branch matches the stage
                    echo "Testing for ${branchName}..."
                    // Your test steps for the branch
                }
            }
        }
        
        stage('Deploy') {
            when {
                expression { branchName in ['b1', 'b2', 'b3'] }
            }
            steps {
                script {
                    // Only execute deployment steps if the branch matches the stage
                    echo "Deploying for ${branchName}..."
                    // Your deployment steps for the branch
                }
            }
        }
    }
    
    post {
        always {
            echo "Pipeline completed for branch: ${branchName}"
        }
    }
}
