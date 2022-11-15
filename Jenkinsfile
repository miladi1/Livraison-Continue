pipeline {
    agent any
    stages{
        stage("git pull"){
            steps{
              
                git branch: 'main', 
                credentialsId: 'c37368d7-184e-48ce-a93d-abf7163ea4ee', 
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
       stage("Docker"){
            steps{
              
            
                 sh  " ansible-playbook ansible/docker.yml -i ansible/inventory/host.yml"
              
            }
         }
    }
}
