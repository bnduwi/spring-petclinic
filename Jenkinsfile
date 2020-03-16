pipeline {
  agent any
  stages {
    stage('Compile') {
      when {
          {
           branch 'master' 
          }
        }      
      steps {        
        sh ' ./mvnw compile'
      }
    }
 
      stages {
    stage('Test') {
      when {
          {
           branch 'master' 
          }
        }      
      steps {        
        sh ' ./mvnw test'
      }
    }
  
  stages {
    stage('Package') {
      when {
          {
           branch 'master' 
          }
        }      
      steps {        
        sh ' ./mvnw package'
      }
    }  
  
  
  
  
  
  }
}
