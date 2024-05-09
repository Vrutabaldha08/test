pipeline {
    agent any
    
    environment {
        branchName = "${env.BRANCH_NAME}"
    }
    
    stages {
        stage('Build') {
            when {
                expression { branchName in ['b1', 'b2', 'b3'] }
            }
            steps {
                echo "Building for ${branchName}..."
                // Your build steps for the branch
            }
        }
        
        stage('Test') {
            when {
                expression { branchName in ['b1', 'b2', 'b3'] }
            }
            steps {
                echo "Testing for ${branchName}..."
                // Your test steps for the branch
            }
        }
        
        stage('Deploy') {
            when {
                expression { branchName in ['b1', 'b2', 'b3'] }
            }
            steps {
                echo "Deploying for ${branchName}..."
                // Your deployment steps for the branch
            }
        }
    }
    
    post {
        always {
            echo "Pipeline completed for branch: ${branchName}"
        }
    }
}
