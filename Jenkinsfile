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
          stage('Deployment') {
                steps {
                    deploy adapters: [tomcat9(credentialsId: 'Tomcatcreds', path: '', url: 'http://54.224.242.238:8080/')], contextPath: 'sampleApp', onFailure: false, war: 'target/*.war'
                        }
                     }
       
             }
        }
