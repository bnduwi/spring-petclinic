pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        
        sh '''
            def result = ./mvnw package
            echo "The resutlt is"
            echo "$result"
          '''
      }
    }
  }
}
