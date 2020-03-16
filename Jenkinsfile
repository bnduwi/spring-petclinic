pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh 'ls -la'
        sh 'mkdir spring-petclinic_master/tmp'
        sh 'mkdir spring-petclinic_master@tmp/tmp'
        sh 'ls -la'
        sh './mvnw package'
        sh 'ls -la'
      }
    }
  }
}
