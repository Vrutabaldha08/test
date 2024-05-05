pipeline {
    agent any
    stages {
        stage('Build and Deploy') {
            steps {
                script {
                    // Check if the branch is 'dev'
                    if (env.BRANCH_NAME == 'dev') {
                        // Build and deploy to development environment
                        sh "mvn -Dmaven.test.failure.ignore=true clean package"
                        // Add any additional steps for deployment to the 'dev' environment
                    }
                    // Check if the branch is 'stage'
                    else if (env.BRANCH_NAME == 'stage') {
                        // Build and deploy to staging environment
                        sh "mvn -Dmaven.test.failure.ignore=true clean package"
                        // Add any additional steps for deployment to the 'stage' environment
                    }
                    // Check if the branch is 'prod'
                    else if (env.BRANCH_NAME == 'prod') {
                        // Build and deploy to production environment
                        sh "mvn -Dmaven.test.failure.ignore=true clean package"
                        // Add any additional steps for deployment to the 'prod' environment
                    }
                }
            }
        }
    }
}
