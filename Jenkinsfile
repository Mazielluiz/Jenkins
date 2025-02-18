pipeline {
    agent any
     tools { 
        nodejs "Node 16.20.2" 
    }
    
    stages {
        stage('Checkout') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/main']], userRemoteConfigs: [[url: 'https://github.com/gfavarelli/AppTestePipe.git']]])
            }
        }
        
        stage('Build') {
            steps {
                sh 'npm install'
                sh 'npm run build'
            }
        }
        
        stage('Run Unit Tests') {
            steps {
                sh 'npm run test'
            }
        }
    }
}