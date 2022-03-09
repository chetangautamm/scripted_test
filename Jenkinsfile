  node {
    def kdm=[ip:20.193.238.113,name:kubeadm,password:kubeadm@1234]
    
    stage('Checkout Source Code') {
        checkout([$class: 'GitSCM', branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[credentialsId: '0280c339-f1a8-48bc-b303-3ec7a661b546', url: 'https://github.com/chetangautamm/arck8s.git']]])
    }

   stage("Azure Cli:KIND(AWS)"){
       sshagent(['kubeadm']){
         script{
           try{
             sh "sshpass -p kdm.password ssh -o StrictHostKeyChecking=no kdm.name@kdm.ip pwd"
           }catch(error){
             sh "sshpass -p kdm.password ssh -o StrictHostKeyChecking=no kdm.name@kdm.ip pwd"
             //sh "sshpass -p kubeadm@1234 ssh -o StrictHostKeyChecking=no kubeadm@20.193.238.113 pwd"
           }
         }
      }
    }
  }
