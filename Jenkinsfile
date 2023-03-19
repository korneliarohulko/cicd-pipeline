pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        script {
          checkout scm
          sh(scripts/build.sh)
        }

      }
    }

  }
  environment {
    registry = 'kornelia22322/cicdhomework'
  }
}