pipeline {
    agent any
    
    tools
    {
       maven "maven_global"
    }
     
    stages {
      stage('checkout') {
           steps {
             
                git branch: 'master', url: 'https://github.com/gowthamshashank/simple-java-maven-app.git'
             
          }
        }
         
     
        
         stage('Execute Maven') {
           steps {
             
                sh 'mvn package'             
          }
        }
        
     stage('Ansible Deploy') {
             
            steps {
                 
           sh "ansible-playbook jenkins.yml -i myinventory -- user ansible --key-file ~/.ssh/id_rsa"
}
}
}
}
