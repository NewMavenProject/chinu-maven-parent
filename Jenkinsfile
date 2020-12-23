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
        git 'https://github.com/NewMavenProject/chinu-maven-parent.git'
        
        }
     }
     
     stage('Generate Build Artifact') {
        steps {
        sh 'mvn clean package'
        
        }
     }
     
     }
    }
