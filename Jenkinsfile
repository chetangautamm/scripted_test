  node {
    stage('Checkout Source Code') {
        checkout([$class: 'GitSCM', branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[credentialsId: '0280c339-f1a8-48bc-b303-3ec7a661b546', url: 'https://github.com/chetangautamm/arck8s.git']]])
    }

   stage("Azure Cli:KIND(AWS)"){
       sshagent(['kubeadm']){
         script{
           try{
             sh "sspass -p kubeadm@1234 ssh -o StrictHostKeyChecking=no kubeadm@20.193.238.113 pwd"
           }catch(error){
             sh "sspass -p kubeadm@1234 ssh -o StrictHostKeyChecking=no kubeadm@20.193.238.113 pwd"
           }
         }
      }
    }
  }
}
