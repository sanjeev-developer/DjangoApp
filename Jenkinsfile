pipeline {
    agent any
    
    stages {

        stage('Github Checkout') {
            steps {
                checkout scmGit(branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/sanjeev-developer/DjangoApp.git']])
            }       
        }

        stage('Docker Build') {
            steps {
                sh 'docker build -t sanjeevdevopdev/todoapp'
            }       
        }
        
    }
}
