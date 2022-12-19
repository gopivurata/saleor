pipeline {
    agent {label 'node'}
    triggers { pollSCM('* * * * *') }
    stages {
        stage('git') {
            steps {
                git branch: 'main', url: 'https://github.com/gopivurata/saleor.git'
            }
        }
        stage('docker') {
            steps {
                sh '''docker info
                  docker image build -t gopivurata/salore-2-dashboard:DEV .
                  docker image push gopivurata/salore-2-dashboard:DEV'''
            }
        }
    }
}