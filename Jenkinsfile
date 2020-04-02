pipeline {
  agent any
  stages {
    stage('Build') {
      when {
       not {
          branch 'master' 
        }
      }
      
      steps {
        sh ' ./mvnw clean'
      }
    }
    
    stage('Test') {
      when {
       not {
          branch 'master' 
        }
      }
      
      steps {        
        sh ' ./mvnw test'
      }
    }
    
    stage('Package') {
      when {
       not {
          branch 'master' 
        }
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
   environment { 
                MyTestVar = 'JenkinsTest'
            }
      when {
       not { 
         branch 'master' 
       }       
      }
   
      steps {
        sh 'echo Hello Mr. $MyTestVar'
        sh 'echo Hello Mr. $(env.MyTestVar}'
        
      }
    }  
  }
  
  post {
    success {
        slackSend channel: '#jenkinsnotify',
                  color: 'good',
                  message: "The pipeline ${currentBuild.fullDisplayName} completed successfully."
    }
    failure {
        slackSend channel: '#jenkinsnotify',
                  color: 'warning',
                  message: "The pipeline ${currentBuild.fullDisplayName} Failed. Details: ${env.JOB_NAME} ${env.BUILD_NUMBER}"
    }
  }  
}
