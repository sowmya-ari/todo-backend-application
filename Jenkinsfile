pipeline {
    agent {
        docker {
            image 'node:6-alpine' 
            args '-p 5000:5000' 
        }
    }
    environment {
        CI = 'true'
    }
    stages {
        stage('changing into a server directory') { 
            steps {
                sh 'cd ./server' 
            }
        }
        stage('Build') {
            steps {
                sh 'npm install' 
            }
        }
        stage('moving in to test folder') {
            steps {
                sh 'cd ./test' 
            }
        }
        stage('Run test'){
            steps {
                sh 'npm test' 
            }
        }
    }
}