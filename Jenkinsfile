pipeline {
  agent any
  
  environment {
        DOCKER_HUB_REPO = "srikanthbommineni/flask"
        CONTAINER_NAME = "flask-hello-world"
        DOCKERHUB_CREDENTIALS=credentials('DOCKERHUB_CREDENTIALS')
        }

  stages {
    stage('Checkout') {
      steps {
        git branch: 'main', credentialsId: 'GITHUB', url: 'https://github.com/srikanthbommineni/flask-hello-world-devops-project.git'      
      }
    }
  }

    stage('Build Docker Image'){
        sh 'docker build -t srikanthbommineni/flask .'
    }
    stage('Build Docker Image1') {
            steps {
              withCredentials([usernameColonPassword(credentialsId: 'DOCKERHUB_CREDENTIALS', variable: 'DOCKERHUB_CREDENTIALS')]) {
              sh "sudo docker login -u srikanthbommineni -p ${DOCKERHUB_CREDENTIALS}"
              //sh 'sudo docker build -t srikanthbommineni/flask .'
            
          }
            }
  }
}

