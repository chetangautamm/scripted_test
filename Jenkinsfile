pipeline {
  environment {
    SITE2_HOSTNAME = "3.111.41.173"
    SITE2_USERNAME = "ubuntu"
    SITE2_PASSWORD = "ubuntu"
  }

  agent any

  node {
    stage('Checkout Source Code') {
        checkout([$class: 'GitSCM', branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[credentialsId: '0280c339-f1a8-48bc-b303-3ec7a661b546', url: 'https://github.com/chetangautamm/arck8s.git']]])
    }

   stage("Azure Cli:KIND(AWS)"){
       sshagent(['kind']){
         script{
           try{
             sh "ssh SITE2_USERNAME@SITE2_HOSTNAME pwd"
           }catch(error){
             sh "ssh SITE2_USERNAME@SITE2_HOSTNAME pwd"
           }
         }
      }
    }
  }
}
