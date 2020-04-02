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
        
        sh 'echo Pulling Git branch count!'
        sh 'git rev-list --count HEAD'
      }
    }  
  }
  
  post {
    success {
        slackSend channel: '#ops-room',
                  color: 'good',
                  message: "The pipeline ${currentBuild.fullDisplayName} completed successfully."
    }
  }  
}
