pipeline {
  agent any
  stages {
    stage('Buzz Build') {
      steps {
        pwsh './jenkins/build.sh'
        archiveArtifacts(artifacts: 'target/*.*jar', fingerprint: true)
      }
    }

    stage('Buzz Test') {
      steps {
        pwsh './jenkins/test-all.sh'
      }
    }

  }
}