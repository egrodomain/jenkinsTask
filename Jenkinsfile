pipeline {
    agent any
        stages {
             stage('Code Checkout') {
                steps {
                        git credentialsId: 'slave1Creds', url: 'https://github.com/egrodomain/jenkinsTask.git'
                         }
                     }
            stage('Maven Build') {
                steps {
                    sh "ls -lart"    
                    sh "mvn clean install"
                    sh "ls -lart target"
                         }
                     }
            stage('Archive Artifacts') {
                steps {
                     archiveArtifacts artifacts: 'target/*.war', followSymlinks: false
                        }
                     }
          
       
             }
        }
