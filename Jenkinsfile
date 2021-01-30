pipeline {
  agent any
  stages {
    stage('Buzz Build') {
      steps {
        pwsh '$BUZZ_NAME '
        pwsh './jenkins/build.sh'
        archiveArtifacts(artifacts: '*', fingerprint: true)
      }
    }

    stage('Fluffy Test') {
      steps {
        pwsh './jenkins/test-all.sh'
      }
    }

    stage('Fluffy Deploy') {
      steps {
        pwsh './jenkins/deploy.sh staging'
      }
    }

  }
}