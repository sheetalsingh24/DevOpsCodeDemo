pipeline{
    
    tools{
        maven 'mymaven'
    }
   // in agent any = any available server 
    agent any
   stages{
       stage('Clone a Repo'){
           steps{
               git 'https://github.com/sheetalsingh24/DevOpsCodeDemo.git'
           }
       }
       
       stage('Compile the code'){
           steps{
               sh 'mvn compile'
           }
       }
       
       stage('CodeReview'){
           steps{
               sh 'mvn pmd:pmd'
           }
       }
       
       stage('Unit Test'){
           steps{
               sh 'mvn test'
           }
       }
       
       stage('Package'){
           steps{
               sh 'mvn package'
           }
       }
       stage('Deploy'){
           steps{
               sh 'sudo cp /var/lib/jenkins/workspace/devops_demo/target/addressbook.war /opt/apache-tomcat-9.0.80/webapps/'
           }
       }
       }
}
