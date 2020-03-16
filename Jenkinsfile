pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        def result = sh './mvnw package'
        sh '''
            echo "The resutlt is"
            echo "$result"
          '''
      }
    }
  }
}
