pipeline {
  agent any
  stages {
    stage('Buzz Build') {
      steps {
        bat './jenkins/build.sh'
      }
    }

    stage('Buzz Test') {
      steps {
        sh './jenkins/test-all.sh'
      }
    }

  }
}