pipeline {
    agent any
    
    stages {
        stage ('Git Clone'){
            steps {
                git credentialsId: 'GITHUB_CREDENTIALS', url: 'https://github.com/SruthiKeerthana/myapp.git'
            }
        }
        stage ('Build Docker Image') {
            steps {
                sh 'docker build -t sruthikeerthana/react-image .'
            }
        }
    }
}
