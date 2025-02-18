pipeline {
    agent any
    tools { 
        nodejs "NodeJS" // Corrigido o nome da ferramenta
    }
    
    stages {
        stage('Checkout') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/main']], userRemoteConfigs: [[url: 'https://github.com/Mazielluiz/Jenkins.git']]])
            }
        }
        
        stage('Build') {
            steps {
                bat 'npm install'
                bat 'npm run build'
            }
        }

        
        stage('Run Unit Tests') {
            steps {
                bat 'npm run test'
            }
        }
    }
}