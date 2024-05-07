pipeline {
    agent any
    
    stages {
        stage('Checkout') {
            steps {
                script {
                    checkout scm
                }
            }
        }
        
        stage('Test') {
            steps {
                echo 'Testing...'
            }
        }
        
        stage('Deploy') {
            steps {
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
    
    if (env.BRANCH_NAME == 'dev' || env.BRANCH_NAME == 'prod') {
        stage('Build') {
            steps {
                echo 'Building...'
            }
        }
    } else {
        stage('Build Skipped') {
            steps {
                echo 'Build stage skipped for branch: ${env.BRANCH_NAME}'
            }
        }
    }
    
    // Debugging: Print branch name
    println "Branch Name: ${env.BRANCH_NAME}"
}
