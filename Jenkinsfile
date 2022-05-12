
pipeline {
    agent any
    environment {
        dockerImage = ''
        registry = 'sesibhushansrijan/sesi24'
    }
    stages {
        stage('Build') {
            steps {
                git url: 'https://github.com/sesibhushan121/samplejenkins.git', branch: 'main',
                 credentialsId: 'git_hub'
            }
        }
        stage('Build docker image') {
            steps {
                script {
                    docker.withRegistry(BuildParams.protocol + "://" + BuildParams.registryUrl, BuildParams.credentials) {
                    dockerImage = BuildParams.dockerRegistryNamespace + "/" + BuildParams.serviceName + ":" + BuildParams.imageTag
                    sh "docker build ${dockerImage} ."
                    sh "docker tag ${dockerImage}  ${BuildParams.registryUrl}/${dockerImage}"
                }
            }
        }
        
    }
}
