pipeline {
  agent any

  stages {
    stage('Checkout') {
      steps {
        checkout scm
        git credentialsId: 'GITHUB', url: 'https://github.com/srikanthbommineni/flask-hello-world-devops-project.git'
      }
    }
