pipeline {
  agent any
  tools {
    nodejs 'node'
  }
  stages {
  
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
