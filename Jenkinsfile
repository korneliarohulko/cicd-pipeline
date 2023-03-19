pipeline {
  agent any
  stages {
    stage('Git Checkout') {
      steps {
        script {
          checkout scm
        }

      }
    }

    stage('Build') {
      steps {
        script {
          checkout scm
          sh 'script scripts/build.sh'
        }

      }
    }

    stage('Test') {
      steps {
        script {
          sh 'script scripts/test.sh'
        }

      }
    }

    stage('Build Image') {
      steps {
        script {
          sh 'docker build -t ${registry}:$BUILD_NUMBER -t ${registry}:latest .'
        }

      }
    }

  }
  environment {
    registry = 'kornelia22322/cicdhomework'
  }
}