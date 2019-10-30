pipeline {
  agent any 
  stages {
    stage('Lint') {
      steps {
        sh 'hadolint Dokerfile'
      }
    }
    stage('Build') {
      steps {
        sh 'docker build --tag=capstone .'
      }
    }
          }
}
