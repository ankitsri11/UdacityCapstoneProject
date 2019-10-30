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
    stage('Push docker image to ECR') {
      steps {
        sh docker.withRegistry("https://719367038294.dkr.ecr.us-west-2.amazonaws.com/udacity", "ecr:us-west-2:deploy") { docker.image("capstone").push() }
      }
    }
  }
}
