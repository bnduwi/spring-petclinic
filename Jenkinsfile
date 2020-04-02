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
      when {
       not {
          branch 'master' 
        }
      }
   
      steps {
        def username = 'Jenkins'
        echo 'Hello Mr. ${username}'
        echo "I said, Hello Mr. ${username}"
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
                  color: 'bad',
                  message: "The pipeline ${currentBuild.fullDisplayName} Failed. Details: ${env.JOB_NAME} ${env.BUILD_NUMBER}"
    }
  }  
}
