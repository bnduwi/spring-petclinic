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
        sh """
            #!/bin/bash
            myvar=git rev-list --count HEAD
            echo "The value is \$myvar"
        """
        sh 'echo Pulling Git branch count!'
        //sh 'git rev-list --count HEAD'
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
                  color: 'good',
                  message: "The pipeline ${currentBuild.fullDisplayName} Failed. Details: ${env.JOB_NAME} ${env.BUILD_NUMBER}"
    }
  }  
}
