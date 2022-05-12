pipeline {
    agent any
    
    environment {
        dockerImage = ''
        registry = 'sesibhushansrijan/sesi24'
        
    }
    stages {
        stage('Build') {
            steps {
                // Get code from a GitHub repository
                git url: 'https://github.com/sesibhushan121/samplejenkins.git', branch: 'main',
                 credentialsId: '	dockerhub_id'
            }
        }
        
        stage('Build docker image') {
            steps {
                script {
                    dockerImage = docker.build registry
                }
            }
        }    
            
        
            
            
    }
}
