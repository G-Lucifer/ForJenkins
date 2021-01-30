pipeline {
  agent any
  stages {
    stage('Buzz Build') {
      steps {
        pwsh './jenkins/build.sh'
        archiveArtifacts(artifacts: '*', fingerprint: true)
        pwsh 'echo "I am a ${BUZZ_NAME}"'
      }
    }

    stage('Buzz Test') {
      steps {
        pwsh './jenkins/test-all.sh'
      }
    }

  }
  environment {
    BUZZ_NAME = 'Worker Bee'
  }
}