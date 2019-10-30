pipeline {
  agent any 
  stages {
    stage('Lint') {
      steps {
        sh 'docker run --rm -i hadolint/hadolint < Dockerfile'
      }
    }
    stage('Build') {
      steps {
        sh 'docker build --tag=capstone .'
      }
    }
          }
}
