pipeline {
    agent any
    
    environment {
        registry = "sruthikeerthana/my-image"
        registryCredentials ="
    
    stages {
        stage ('Git Clone'){
            steps {
                git credentialsId: 'GITHUB_CREDENTIALS', url: 'https://github.com/SruthiKeerthana/myapp.git'
            }
        }
        stage ('Build Docker Image') {
            steps {
                sh 'docker build -t sruthikeerthana/react-image:${BUILD_NUMBER} .'
            }
        }
        stage ('Docker Login and Push') {
            steps {
              withCredentials([string(credentialsId: 'DOCKERHUB_CREDENTIALS', variable: 'DOCKERHUB_CREDENTIALS')]) {
                sh 'docker login -u sruthikeerthana -p ${DOCKERHUB_CREDENTIALS}'
                
                  sh 'docker push sruthikeerthana/react-image:${BUILD_NUMBER}'
              }
            }
        }
    }
}
