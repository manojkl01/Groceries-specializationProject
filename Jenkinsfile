pipeline {
    agent any
    tools {
         maven 'maven3'
    }
    stages{
        stage('Build'){
            steps{
                 cleanWs()
                 checkout scm
                echo "Building ${env.project1}..."
            }
        }
     stage('Upload War To Nexus'){
            steps{
                nexusArtifactUploader artifacts:[
                   [
                        artifactId: 'Groceryrepo1',
                       classifier: '',
                       file: '/var/lib/jenkins/jobs/GroceryStore1/config.xml',
                      type: 'war'
                 ]
             ],
                   credentialsId: '1b207162-1d0d-4008-a8ee-4c19cbb0887d',
                   groupId: 'Groceryrepo1',
                   nexusUrl: '65.2.61.50:8081',
                   nexusVersion: 'nexus3',
                   protocol: 'http',
                   repository: 'maven-snapshots',
                   version: '1.0-SNAPSHOT'
  
            }
        }
    }
}
