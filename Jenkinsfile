pipeline {
  agent any

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
                sh 'docker image build -t $DOCKER_HUB_REPO:latest .'
            }
        }
  }
}
