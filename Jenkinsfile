pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        withGradle() {
          build(job: 'build', propagate: true, quietPeriod: 5, wait: true)
        }

      }
    }

    stage('archive') {
      steps {
        archiveArtifacts(defaultExcludes: true, onlyIfSuccessful: true, artifacts: 'bin/*.jar')
      }
    }

  }
}