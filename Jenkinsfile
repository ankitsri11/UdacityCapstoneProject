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
        sh docker.withRegistry("https://us-west-2.console.aws.amazon.com", "ecr:us-west-2:deploy") { docker.image("capstone").push() }
      }
    }
  }
}
