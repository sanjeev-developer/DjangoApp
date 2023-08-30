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
                sh 'docker build -t sanjeevdevopdev/todoapp .'
            }       
        }

        stage('Docker push') {
            steps {
                script{
                    withCredentials([string(credentialsId: 'dockerpass', variable: 'dockerpassword')]) {
                        sh 'docker login -u sanjeevgupta9223@gmail.com -p ${dockerpassword}'
                    }
                    sh 'docker push sanjeevdevopdev/todoapp'
                }   
            }
        }
    }
}
