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

    stage('Testing A') {
      parallel {
        stage('Buzz Test') {
          steps {
            pwsh './jenkins/test-all.sh'
          }
        }

        stage('Testing B') {
          steps {
            powershell 'sleep 5; echo \'done a\''
          }
        }

      }
    }

  }
  environment {
    BUZZ_NAME = 'Worker Bee'
  }
}