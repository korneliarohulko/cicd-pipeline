pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        script {
          checkout scm
          .scripts/build.sh
        }

      }
    }

  }
  environment {
    registry = 'kornelia22322/cicdhomework'
  }
}