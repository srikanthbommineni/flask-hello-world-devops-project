pipeline {
  agent any
  
  environment {
        DOCKER_HUB_REPO = "srikanthbommineni/flask"
        CONTAINER_NAME = "flask-hello-world"
        }

  stages {
    stage('Checkout') {
      steps {
        git branch: 'main', credentialsId: 'GITHUB', url: 'https://github.com/srikanthbommineni/flask-hello-world-devops-project.git'      
      }
    }
    stage('Build Docker Image') {
            steps {
              sh 'docker build -t $DOCKER_HUB_REPO .'
            }
        }
  }
}
