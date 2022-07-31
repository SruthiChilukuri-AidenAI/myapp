pipeline {
    agent any
    
    environment {
        registry = "sruthikeerthana/my-image"
        registryCredentials ="DOCKERHUB_CREDENTIALS"
        dockerImage = ''
    }
    
    stages {
        stage ('Git Clone'){
            steps {
                git credentialsId: 'GITHUB_CREDENTIALS', url: 'https://github.com/SruthiKeerthana/myapp.git'
            }
        }
        stage ('Build Docker Image') {
            steps {
                script{
                    dockerImage = docker.build registry + ":${BUILD_NUMBER}"
                }
            }
        }
        stage ('Docker Login and Push') {
            steps {
                script {
                    docker.withRegistry( '', registryCredential ) {
                         dockerImage.push()
                     }
                }
            }
        }
    }
}
