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
    stage('Build image') {
      steps {
        app = docker.build("kirillvr/test")
      }
    }
    stage('Test') {
      steps {
         bat 'node app.js'
      }
    }   
  }
}
