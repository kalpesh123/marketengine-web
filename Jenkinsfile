pipeline {
    agent any
    
    tools{
        jdk 'jdk11'
        nodejs 'node16'
        
    }    
  
    stages {
        stage('Git Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/kalpesh123/marketengine-web.git'
            }
        }     
  
        stage('install & Build') {
            steps {
                dir('/root/.jenkins/workspace/marketengine-web/app') {
                    sh "npm install"
                }
            }
        }
        
        stage('Deploy to Conatiner') {
            steps {
                sh "npm run compose:up -d"
            }
        }
    }
}