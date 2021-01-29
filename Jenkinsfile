pipeline {
  agent any
  stages {
    stage('Buzz Buzz') {
      steps {
        echo 'buzz buzzz'
      }
    }

    stage('Bees Bees') {
      steps {
        echo 'BEEs beez'
        echo 'beess buzzing'
      }
    }

    stage('Fluffy Build') {
      steps {
        echo 'placeholder'
        bat 'echo another placeholder'
      }
    }

    stage('Fluffy Test') {
      steps {
        bat 'sleep 5'
        bat 'echo success'
      }
    }

    stage('Fluffy Deploy') {
      steps {
        echo 'placeholder'
      }
    }

  }
}