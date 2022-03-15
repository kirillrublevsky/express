pipeline {
  agent any
  tools {
    nodejs 'node'
  }
  stages {
    stage('Cloning Git') {
      steps {
        git 'https://github.com/kirillrublevsky/express'
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
