pipeline {
    agent any
    stages{
        stage("git pull"){
            steps{
              
                git branch: 'main', 
                credentialsId: '7a11751d-b52e-4b05-9c01-6c8ab6bd2941', 
                url: 'https://github.com/miladi1/Livraison-Continue.git'
                    
                }
                
            }
      stage("Build"){
            steps{
              
              script {
                 sh  "ansible-playbook ansible/build.yml -i ansible/inventory/host.yml"
              }
            }
         }
    }
}
