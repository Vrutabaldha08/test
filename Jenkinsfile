pipeline {
    agent any
    
    environment {
        // Define a variable to store the branch name
        branchName = "${env.BRANCH_NAME}"
    }
    
    stages {
        stage('Build') {
            when {
                // Only execute this stage if the branch is 'dev'
                expression { branchName == 'dev' }
            }
            steps {
                // Your build steps here
                echo 'Building...'
            }
        }
        
        stage('Test') {
            when {
                // Only execute this stage if the branch is 'stage'
                expression { branchName == 'stage' }
            }
            steps {
                // Your test steps here
                echo 'Testing...'
            }
        }
        
        stage('Deploy') {
            when {
                // Only execute this stage if the branch is 'prod'
                expression { branchName == 'prod' }
            }
            steps {
                // Your deployment steps here
                echo 'Deploying...'
            }
        }
    }
}
