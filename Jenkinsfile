pipeline{
    agent any
    tools {
       maven 'maven3'
         }
    stages{
        stage('checkoutcode'){
        steps{
            git 'https://github.com/chinnareddaiah/simple-app.git'
        }
        }
        stage('maven build'){
        steps{
            sh 'mvn clean package'
        
        }
        }
    }
}
