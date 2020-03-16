pipeline {
  agent any
  stages {
    stage('Compile') {
      when {
        branch 'master'
      }      
      steps {        
        sh ' ./mvnw compile'
      }
    }
    stage('Test') {
      when {
        branch 'master'
      }      
      steps {        
        sh ' ./mvnw test'
      }
    }
    stage('Package') {
      when {
        branch 'master' 
      }      
      steps {        
        sh ' ./mvnw package'
      }
    }  
  }
}
