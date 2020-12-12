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
        stage('upload artifcat to nexus'){
            steps{
                nexusArtifactUploader artifacts: [
                    [
                        artifactId: 'sample-app', 
                        classifier: '', file: 'target/simple-app-1.0.0-RELESE.war', 
                        type: 'war'
                    ]
                ], 
                credentialsId: 'nexus3', 
                groupId: 'in.javahome', 
                nexusUrl: '172.31.8.187', 
                nexusVersion: 'nexus3', 
                protocol: 'http', 
                repository: 'sampleapp-release', 
                version: '1.0.0'
            }
        }
    }
}
