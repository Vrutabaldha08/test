pipeline {
    agent any
    
    stages {
        stage('Checkout') {
            steps {
                // Checkout code from the respective branch
                script {
                    checkout scm
                }
            }
        }
        
        stage('Build') {
            when {
                expression {
                    env.BRANCH_NAME == 'dev' || env.BRANCH_NAME == 'prod' || env.BRANCH_NAME == 'stage'
                }
            }
            steps {
                // Your build steps for all branches
            }
        }
        
        stage('Test') {
            when {
                expression {
                    env.BRANCH_NAME == 'dev' || env.BRANCH_NAME == 'prod' || env.BRANCH_NAME == 'stage'
                }
            }
            steps {
                // Your test steps for all branches
            }
        }
        
        stage('Deploy') {
            when {
                expression {
                    env.BRANCH_NAME == 'dev' || env.BRANCH_NAME == 'prod' || env.BRANCH_NAME == 'stage'
                }
            }
            steps {
                // Your deployment steps for all branches
            }
        }
    }
}
