pipeline {
   agent any
   
options {
  buildDiscarder logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr: '', daysToKeepStr: '', numToKeepStr: '5')
}

   tools {
  maven 'Maven 3.6.3'
}

   stages {
     
     stage('Code Checkout') {
        steps {
        git credentialsId: 'git', url: 'https://github.com/Devops2272/New-Maven-Branch.git'
        
        }
     }
     
     stage('Generate Build Artifact') {
        steps {
        sh 'mvn clean package'
        
        }
     }
     
     }
    }
