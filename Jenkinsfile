
peline {
    agent any
    stages {
        stage('Build-dev') {
            when { branch 'develop'}
            steps {      
                sh 'echo "Start Development server deployment"'      
                sh "mvn -Dmaven.test.failure.ignore=true clean package"
                script{
                 app = docker.build("zonemsp_document_upload_service_dev")
                }
            }   
        }

         stage('Deploy-dev') {
            when { branch 'develop'}
            steps {
                script{
                        docker.withRegistry('https://631289223051.dkr.ecr.us-east-1.amazonaws.com', 'ecr:us-east-1:aws-credentials') {
                    app.push("${env.BUILD_NUMBER}")
                            app.push("latest")
                    }
                }
            }
         }
        stage('Login to remote host-dev') {
            when { branch 'develop'}
            steps {
           sshagent(['44.196.158.97']) {
           sh 'pwd'
           sh 'ssh -o StrictHostKeyChecking=no ubuntu@44.196.158.97 "sh /home/ubuntu/script/document-start.sh"'
           }
      }
    }
    stage('Build-stage') {
        when { branch 'staging'}
        steps {
            sh 'echo "Start staging server deployment"'
            sh "mvn -Dmaven.test.failure.ignore=true clean package"
            script{
             app = docker.build("zonemsp_document_upload_service_stage")
            }
        }   
    }

     stage('Deploy-stage') {
          when { branch 'staging'}
        steps {
            script{
                    docker.withRegistry('https://631289223051.dkr.ecr.me-central-1.amazonaws.com', 'ecr:me-central-1:aws-credentials') {
                app.push("${env.BUILD_NUMBER}")
                        app.push("latest")
                }
            }
        }
     }
    stage('Login to remote host-stage') {
         when { branch 'staging'}
        steps {
       sshagent(['51.112.12.48']) {
       sh 'pwd'
       sh 'ssh -o StrictHostKeyChecking=no ubuntu@51.112.12.48 "sh /home/ubuntu/script/document-start.sh"'
       }
  }
}
stage('Build-prod') {
     when { branch 'production'}
    steps {
        sh 'echo "Start Production server deployment"'
        sh "mvn -Dmaven.test.failure.ignore=true clean package"
        script{
         app = docker.build("zonemsp_document_upload_service")
        }
    }   
}

 stage('Deploy-prod') {
     when { branch 'production'}
    steps {
        script{
                docker.withRegistry('https://631289223051.dkr.ecr.me-central-1.amazonaws.com', 'ecr:me-central-1:aws-credentials') {
            app.push("${env.BUILD_NUMBER}")
                    app.push("latest")
            }
        }
    }
 }
stage('Login to remote host-prod') {
    when { branch 'production'}
    steps {
   sshagent(['3.29.154.169']) {
   sh 'pwd'
   sh 'ssh -o StrictHostKeyChecking=no ubuntu@3.29.154.169 "sh /home/ubuntu/script/document-start.sh"'
   }
}
}
    }


post {
             always {
              cleanWs(cleanWhenNotBuilt: false,
                    deleteDirs: true,
                    disableDeferredWipeout: true,
                    notFailBuild: true,
                    patterns: [[pattern: '.gitignore', type: 'INCLUDE'],
                               [pattern: '.propsfile', type: 'EXCLUDE']])
        }


            }
        }

