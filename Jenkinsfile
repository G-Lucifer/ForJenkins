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
      parallel {
        stage('Fluffy Test') {
          steps {
            pwsh './jenkins/test-all.sh'
          }
        }

        stage('Backend') {
          steps {
            pwsh './jenkins/test-backend.sh'
          }
        }

        stage('frontend') {
          steps {
            pwsh './jenkins/test-frontend.sh'
          }
        }

        stage('performance') {
          steps {
            pwsh './jenkins/test-performance.sh'
          }
        }

        stage('static') {
          steps {
            pwsh './jenkins/test-static.sh'
          }
        }

      }
    }

    stage('Fluffy Deploy') {
      steps {
        pwsh './jenkins/deploy.sh staging'
      }
    }

  }
}