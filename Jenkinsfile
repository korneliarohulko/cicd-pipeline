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

    stage('Push Image') {
      steps {
        script {
          docker.withRegistry('', 'dockerhub_id') {
            docker.image("${registry}:${env.BUILD_ID}").push('latest')
            docker.image("${registry}:${env.BUILD_ID}").push("${env.BUILD_ID}")
          }
        }

      }
    }

  }
  environment {
    registry = 'kornelia22322/cicd'
  }
}