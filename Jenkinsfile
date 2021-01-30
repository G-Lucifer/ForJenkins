pipeline {
  agent any
  stages {
    stage('Buzz Build') {
      steps {
        pwsh './jenkins/build.sh'
      }
    }

    stage('Buzz Test') {
      steps {
        pwsh './jenkins/test-all.sh'
      }
    }

  }
}