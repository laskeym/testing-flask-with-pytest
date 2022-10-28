pipeline {
  options {
    buildDiscarder(logRotator(numToKeepStr: '10')) // Retain history on the last 10 builds
    ansiColor('xterm') // Enable colors in terminal
    timestamps() // Append timestamps to each line
    timeout(time: 20, unit: 'MINUTES') // Set a timeout on the total execution time of the job
  }
  
  stages {
    stage('pylint') {
      steps {
        script {
          sh """
          pylint ./*.py
          """
        }
      }
    }
    stage('pytest') {
      steps {
        script {
          sh """
          pytest
          """
        }
      }
    }
  }
}