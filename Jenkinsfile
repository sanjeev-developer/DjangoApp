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
                    withCredentials([string(credentialsId: 'docker-new-login', variable: 'docker_new_login')]) {
                        sh 'docker login -u sanjeevgupta9223@gmail.com -p ${docker_new_login}'
                    }
                    sh 'docker push sanjeevdevopdev/todoapp'
                }   
            }
        }

        stage('Docker compose up') {
            steps {
                sh 'docker-compose -f sanjeev-compose.yml up -d'
            }       
        }
    }
}
