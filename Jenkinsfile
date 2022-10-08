pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        build(job: 'compile', propagate: true, quietPeriod: 5, wait: true)
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