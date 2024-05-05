pipeline {
    agent any
    stages {
        stage('Build') {
            when {
                expression { env.BRANCH_NAME == 'dev' || env.BRANCH_NAME == 'stage' || env.BRANCH_NAME == 'prod' }
            }
            steps {
                script {
                    // Add build steps specific to each branch if necessary
                    echo "Building ${env.BRANCH_NAME} branch"
                }
            }
            displayName "${env.BRANCH_NAME == 'dev' ? 'Build-dev' : env.BRANCH_NAME == 'stage' ? 'Build-stage' : 'Build-prod'}"
        }
        stage('Deploy') {
            when {
                expression { env.BRANCH_NAME == 'dev' || env.BRANCH_NAME == 'stage' || env.BRANCH_NAME == 'prod' }
            }
            steps {
                script {
                    // Add deploy steps specific to each branch if necessary
                    echo "Deploying ${env.BRANCH_NAME} branch"
                }
            }
            displayName "${env.BRANCH_NAME == 'dev' ? 'Deploy-dev' : env.BRANCH_NAME == 'stage' ? 'Deploy-stage' : 'Deploy-prod'}"
        }
        stage('Staging') {
            when {
                expression { env.BRANCH_NAME != 'dev' }
            }
            steps {
                script {
                    // Add staging steps specific to the branch if necessary
                    echo "Staging ${env.BRANCH_NAME} branch"
                }
            }
            displayName "${env.BRANCH_NAME == 'stage' ? 'Staging-stage' : env.BRANCH_NAME == 'prod' ? 'Staging-prod' : 'Staging-${env.BRANCH_NAME}'}"
        }
    }
}
