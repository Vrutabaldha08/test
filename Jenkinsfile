pipeline {
    agent any
    stages {
        stage('Build') {
            when {
                expression {
                    return env.BRANCH_NAME == 'dev' || env.BRANCH_NAME == 'stage' || env.BRANCH_NAME == 'prod'
                }
            }
            steps {
                script {
                    sh "echo 'Start Build for ${env.BRANCH_NAME} branch'"
                    // Add any build steps specific to the branch
                }
            }
            displayName "Build-${env.BRANCH_NAME}"
        }
        stage('Deploy') {
            when {
                expression {
                    return env.BRANCH_NAME == 'dev' || env.BRANCH_NAME == 'stage' || env.BRANCH_NAME == 'prod'
                }
            }
            steps {
                script {
                    sh "echo 'Start Deploy for ${env.BRANCH_NAME} branch'"
                    // Add any deploy steps specific to the branch
                }
            }
            displayName "Deploy-${env.BRANCH_NAME}"
        }
        stage('Stage') {
            when {
                expression {
                    return env.BRANCH_NAME == 'dev' || env.BRANCH_NAME == 'stage' || env.BRANCH_NAME == 'prod'
                }
            }
            steps {
                script {
                    sh "echo 'Start Stage for ${env.BRANCH_NAME} branch'"
                    // Add any staging steps specific to the branch
                }
            }
            displayName "Stage-${env.BRANCH_NAME}"
        }
    }
}
