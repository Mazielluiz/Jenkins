pipeline {
    agent any
     tools { 
        nodejs "Node 23.8.0" 
    }
    
    stages {
        stage('Checkout') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/main']], userRemoteConfigs: [[url: 'https://github.com/Mazielluiz/Jenkins.git']]])
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