pipeline {
  environment { 
    def registry = "YourDockerhubAccount/YourRepository" 
    def registryCredential = 'dockerhub_id' 
    def app = '' 
  }
  agent any
  tools {
    nodejs 'node'
  }
  stages {
    stage('Clone repository') {
      steps {
        git 'https://github.com/kirillrublevsky/express.git'
      }        
    }  
    stage('Install') {
      steps {
        bat 'npm i -save express'
      }
    }
     stage('Test') {
      steps {
         bat 'node app.js'
      }
    }   
  }
}
