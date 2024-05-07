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
        
        script {
            if (env.BRANCH_NAME == 'dev' || env.BRANCH_NAME == 'prod') {
                stage('Build') {
                    steps {
                        // Your build steps for 'dev' and 'prod' branches
                        echo 'Building...'
                    }
                }
            }
        }
        
        stage('Test') {
            steps {
                // Your test steps for all branches
                echo 'Testing...'
            }
        }
        
        stage('Deploy') {
            steps {
                // Your deployment steps for all branches
                echo 'Deploying...'
            }
        }
    }
    
    post {
        always {
            script {
                currentBuild.result = currentBuild.result ?: 'SUCCESS'
            }
        }
    }
}
