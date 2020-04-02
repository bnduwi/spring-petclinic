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
      steps {        
        // slackSend baseUrl: 'https://hooks.slack.com/services/', channel: 'jenkins-notifications', color: 'good', message: 'Build Successful on${env.JOB_NAME} ${env.BUILD_NUMBER}', tokenCredentialId: 'slack-demo-message'
      }
    }
  
  }
}
