pipeline {
  options {
    ansiColor('xterm') // Enable colors in terminal
    timestamps() // Append timestamps to each line
  }
  stages {
    stage('pylint') { // Linter
      steps {
        script {
          sh 'pylint ./*.py'
        }
      }
    }
    stage('pytest') { // Unit Tests
      steps {
        script {
          sh 'pytest test_api.py'
        }
      }
    }
  }
}
