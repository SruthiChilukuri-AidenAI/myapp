pipeline {
    agent any
    
    stages {
        stage ('Git Clone'){
            steps {
                git credentialsId: 'GITHUB_CREDENTIALS', url: 'https://github.com/SruthiKeerthana/myapp.git'
            }
        }
    }
}
