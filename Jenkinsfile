pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        
        sh '''
            result = ./mvnw package
            echo "The resutlt is"
            echo "$result"
          '''
      }
    }
  }
}
