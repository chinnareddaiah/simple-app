pipeline{
    agent any
    tools {
       maven 'maven'
         }
    stages{
        stage('checkoutcode'){
        steps{
            git 'https://github.com/chinnareddaiah/simple-app.git'
        }
        }
        stage('maven build'){
        steps{
            sh script: 'mvn clean package'
        
        }
        }
    }
}
