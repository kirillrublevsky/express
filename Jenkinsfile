pipeline {
  agent any
  tools {
    nodejs 'node'
  }
  stages {
    stage('Clone repository') {
        checkout scm
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
