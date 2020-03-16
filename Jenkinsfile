pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        def result = sh './mvnw package'
        echo 'The resutlt is'
        echo result
      }
    }
  }
}
