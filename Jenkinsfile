pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh 'ls -la'
        sh 'mkdir ./tmp'
        sh 'ls -la'
        sh './mvnw package'
        sh 'ls -la'
      }
    }
  }
}
