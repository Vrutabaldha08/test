pipeline {
    agent any
    
    environment {
        branchName = "${env.BRANCH_NAME}"
    }

    // Check if the branch is not dev, stage, or prod
    if (!(branchName in ['dev', 'stage', 'prod'])) {
        stages {
            stage('Skip') {
                steps {
                    echo "Skipping pipeline execution for branch: ${branchName}"
                }
            }
        }
        return // Exit early
    }

    // If the branch is dev, stage, or prod, continue with the pipeline execution
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
