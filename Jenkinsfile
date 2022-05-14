pipeline {  
    environment {
        registry = "sesibhushansrijan/sesi244"
        registryCredential = 'dockerhub'
    }  
 
    agent any  
    
    stages {
      
         stage('Building image') {
             steps{
                script {
                     docker.build registry + ":$BUILD_NUMBER"
                }
            }
        }
    }    
} 
