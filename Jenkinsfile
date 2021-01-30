pipeline {
  agent any
  stages {
    stage('Buzz Build') {
      steps {
        pwsh './jenkins/build.sh'
        archiveArtifacts(artifacts: '*.*', fingerprint: true)
      }
    }

    stage('Buzz Test') {
      steps {
        pwsh './jenkins/test-all.sh'
        junit 'C:/WINDOWS/System32/config/systemprofile/AppData/Local/Jenkins/.jenkins/jobs/ForJenkins/branches/simple-pipeline/**/*.xml'
      }
    }

  }
}