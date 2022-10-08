pipeline {
  agent any
  stages {
    stage('archive') {
      steps {
        echo 'Pipeline run!'
        withGradle() {
          build 'build'
        }

      }
    }

  }
}