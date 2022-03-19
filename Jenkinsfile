pipeline {
  environment { 
    def registry = "kirillvr/test" 
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
        script {
          app = docker.build registry + ":$BUILD_NUMBER"
        }
      }
    }
    stage('Test image') {
      steps {
        script {
          app.inside {
            bat 'echo "Tests passed"'
          }
        }
      }
    }
    stage('Push image') {
      steps {
        script {
          docker.withRegistry('https://registry.hub.docker.com', registryCredential) {
            app.push("${env.BUILD_NUMBER}")
            app.push("latest")
          }
        }
      }
    }
    stage('Cleaning up') { 
      steps { 
        bat "docker rmi $registry:$BUILD_NUMBER" 
      }
    } 
  }
}
