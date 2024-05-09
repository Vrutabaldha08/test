pipeline {
    agent any
    
    environment {
        branchName = "${env.BRANCH_NAME}"
    }

    // Check if the branch is not b1, b2, or b3
    if (!(branchName in ['b1', 'b2', 'b3'])) {
        stages {
            stage('Skip') {
                steps {
                    echo "Skipping pipeline execution for branch: ${branchName}"
                }
            }
        }
        return // Exit early
    }

    // If the branch is b1, b2, or b3, continue with the pipeline execution
    stages {
        stage('Build') {
            steps {
                echo "Building for ${branchName}..."
                // Your build steps for the branch
            }
        }
        
        stage('Test') {
            steps {
                echo "Testing for ${branchName}..."
                // Your test steps for the branch
            }
        }
        
        stage('Deploy') {
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
