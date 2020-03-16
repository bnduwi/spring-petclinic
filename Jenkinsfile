pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh 'mkdir tmp'
        sh './mvnw package'
      }
    }
  }
}
