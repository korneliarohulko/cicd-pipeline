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

  }
  environment {
    registry = 'kornelia22322/cicdhomework'
  }
}