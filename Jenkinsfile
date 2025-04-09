
pipeline{
    
    tools{
        maven 'mymaven'
    }
   // in agent any = any available server 
    agent none
   stages{
       stage('Clone a Repo'){
         agent {label 'linux_node'}
           steps{
               git 'https://github.com/puritanviitm/jenkins-demo.git'
           }
       }
       
       stage('Compile the code'){
         agent any
           steps{
               sh 'mvn compile'
           }
       }
       
       stage('CodeReview'){
         agent {label 'linux_node'}
           steps{
               sh 'mvn pmd:pmd'
           }
       }
       
       stage('Unit Test'){
         agent {label 'linux_node'}
           steps{
               sh 'mvn test'
           }
       }
       
       stage('Package'){
         agent any
           steps{
               sh 'mvn package'
           }
       }
       }
}
