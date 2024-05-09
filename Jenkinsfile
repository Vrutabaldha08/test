pipeline {
    agent any
    
    environment {
        branchName = "${env.BRANCH_NAME}"
    }

    stages {
        stage('Check Branch') {
            steps {
                script {
                    // Check if the branch is not dev, stage, or prod
                    if (!(branchName in ['dev', 'stage', 'prod'])) {
                        echo "Branch not found in Jenkinsfile"
                        error "Unsupported branch: ${branchName}"
                    }
                }
            }
        }

        stage('Build') {
            when {
                expression { branchName in ['dev', 'stage', 'prod'] }
            }
            steps {
                echo "Building for ${branchName}..."
                // Your build steps for the branch
            }
        }
        
        stage('Test') {
            when {
                expression { branchName in ['dev', 'stage', 'prod'] }
            }
            steps {
                echo "Testing for ${branchName}..."
                // Your test steps for the branch
            }
        }
        
        stage('Deploy') {
            when {
                expression { branchName in ['dev', 'stage', 'prod'] }
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
