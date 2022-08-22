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
                        sh "mvn clean install"
                         }
                     }
       
             }
        }
