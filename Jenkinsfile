pipeline {
  agent any
  stages {
    stage('Build') {
      when {
        branch 'master'
      }      
      steps {        
        sh ' ./mvnw clean'
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
    stage('Deploy') {
      when {
       not {
          branch 'master' 
        }
      }      
      steps {        
        sh ' ./mvnw package'
      }
    }
    
 stage('Done!') {
      when {
          branch 'master'
      }      
      steps {        
        slackSend channel: 'jenkins-notifications', color: 'good', message: 'Build Successful - ${BUILD_URL}', tokenCredentialId: 'slack-demo-message'
      }
    }
  
  }
}
