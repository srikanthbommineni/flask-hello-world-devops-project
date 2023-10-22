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
        checkout scm
        git credentialsId: 'GITHUB', url: 'https://github.com/srikanthbommineni/flask-hello-world-devops-project.git'
      }
    }
    stage('Build') {
            steps {
                echo 'Building..'
                sh 'docker build -t $DOCKER_HUB_REPO:latest .'
            }
        }
  }
}
