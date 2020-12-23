pipeline {
   agent any
   
options {
  buildDiscarder logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr: '', daysToKeepStr: '', numToKeepStr: '5')
}

   tools {
  maven 'Maven 3.6.3'
}
stages {
     
     
   
     
     stage('Generate Build Artifact') {
        steps {
        sh 'mvn clean package'
        
        }
     }
     
      stage('Send Build for Docker Image'){
      
         steps{
          
           sshPublisher(publishers: [sshPublisherDesc(configName: 'Docker', transfers: [sshTransfer(cleanRemote: false, excludes: '', execCommand: '', execTimeout: 120000, flatten: false, makeEmptyDirs: false, noDefaultExcludes: false, patternSeparator: '[, ]+', remoteDirectory: '', remoteDirectorySDF: false, removePrefix: '', sourceFiles: '**/*.jar')], usePromotionTimestamp: false, useWorkspaceInPromotion: false, verbose: false)])
             
         }
      } 
      
     }
   post {
    always {
      cleanWs cleanWhenNotBuilt: false, notFailBuild: true
           }
         }
  
}
