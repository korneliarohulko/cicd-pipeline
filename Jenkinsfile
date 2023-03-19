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

  }
  environment {
    registry = 'kornelia22322/cicdhomework'
  }
}