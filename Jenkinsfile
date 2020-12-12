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
                script{
                    def mavenPom = readMavenPom file='pom'
                    nexusArtifactUploader artifacts: [
                    [
                        artifactId: 'sample-app', 
                        classifier: '', 
                        file: "target/simple-app-${mavenPom.version}.war", 
                        type: 'war'
                    ]
                ], 
                credentialsId: 'nexus3', 
                groupId: 'in.javahome', 
                nexusUrl: '13.233.6.247:8081', 
                nexusVersion: 'nexus3', 
                protocol: 'http', 
                repository: 'sampleapp-release', 
                version: "${mavenPom.version}"
                
            }
        }
    }
}
