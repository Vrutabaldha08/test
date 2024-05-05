pipeline {
    agent any
    when {
        // Specify branches to run the pipeline
        expression { env.BRANCH_NAME == 'dev' || env.BRANCH_NAME == 'stage' || env.BRANCH_NAME == 'prod' }
    }
    stages {
        stage('Build') {
            steps {
                script {
                    // Add build steps specific to each branch if necessary
                    echo "Building ${env.BRANCH_NAME} branch"
                }
            }
        }
        stage('Deploy') {
            steps {
                script {
                    // Add deploy steps specific to each branch if necessary
                    echo "Deploying ${env.BRANCH_NAME} branch"
                }
            }
        }
        stage('Staging') {
            when {
                expression { env.BRANCH_NAME == 'stage' }
            }
            steps {
                script {
                    // Add staging steps specific to the 'stage' branch if necessary
                    echo "Staging ${env.BRANCH_NAME} branch"
                }
            }
        }
    }
}
