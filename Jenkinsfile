pipeline {
    agent any
    
    environment {
        // Define a variable to store the branch name
        branchName = "${env.BRANCH_NAME}"
    }
    
    stages {
        stage('Build') {
            steps {
                // Only execute build steps if the branch matches the stage
                script {
                    if (branchName == 'b1') {
                        echo 'Building for b1...'
                        // Your build steps for b1 branch
                    } else if (branchName == 'b2') {
                        echo 'Building for b2...'
                        // Your build steps for b2 branch
                    } else if (branchName == 'b3') {
                        echo 'Building for b3...'
                        // Your build steps for b3 branch
                    }
                }
            }
        }
        
        stage('Test') {
            steps {
                // Only execute test steps if the branch matches the stage
                script {
                    if (branchName == 'b1') {
                        echo 'Testing for b1...'
                        // Your test steps for b1 branch
                    } else if (branchName == 'b2') {
                        echo 'Testing for b2...'
                        // Your test steps for b2 branch
                    } else if (branchName == 'b3') {
                        echo 'Testing for b3...'
                        // Your test steps for b3 branch
                    }
                }
            }
        }
        
        stage('Deploy') {
            steps {
                // Only execute deployment steps if the branch matches the stage
                script {
                    if (branchName == 'b1') {
                        echo 'Deploying for b1...'
                        // Your deployment steps for b1 branch
                    } else if (branchName == 'b2') {
                        echo 'Deploying for b2...'
                        // Your deployment steps for b2 branch
                    } else if (branchName == 'b3') {
                        echo 'Deploying for b3...'
                        // Your deployment steps for b3 branch
                    }
                }
            }
        }
    }
}
