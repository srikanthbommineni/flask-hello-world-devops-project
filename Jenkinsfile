pipeline {
  agent any
  
  environment {
        DOCKER_HUB_REPO = "srikanthbommineni/flask"
        CONTAINER_NAME = "flask-hello-world"
        DOCKERHUB_CREDENTIALS=credentials('dockerhub-credentials')
    }

  stages {
    stage('Checkout') {
      steps {
        git url: ''https://github.com/srikanthbommineni/flask-hello-world-devops-project.git',branch: 'main'      
      }
    }
    stage('Build Docker Image') {
            steps {
              sh 'docker build -t $DOCKER_HUB_REPO .'
            }
        }
  }
}
