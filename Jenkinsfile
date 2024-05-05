pipeline {
    agent any
    stages {
        stage('Build') {
            when {
                anyOf {
                    branch 'dev'
                    branch 'stage'
                    branch 'prod'
                }
            }
            steps {
                script {
                    // Add build steps specific to each branch if necessary
                    echo "Building ${env.BRANCH_NAME} branch"
                }
            }
        }
        stage('Deploy') {
            when {
                anyOf {
                    branch 'dev'
                    branch 'stage'
                    branch 'prod'
                }
            }
            steps {
                script {
                    // Add deploy steps specific to each branch if necessary
                    echo "Deploying ${env.BRANCH_NAME} branch"
                }
            }
        }
        stage('Staging') {
            when {
                branch 'stage'
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
