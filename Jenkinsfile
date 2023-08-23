pipeline {
    agent any
    
    stages {
        stage('Github Checkout') {
            steps {
                checkout scmGit(branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/sanjeev-developer/DjangoApp.git']])
            }
            phone restart kr rha hu wait
        }
        
    }
}
