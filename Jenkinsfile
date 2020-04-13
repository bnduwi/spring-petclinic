pipeline {
  agent any
  stages {
    stage('Build') {
      environment { 
                CurrentCommitHash = """${sh(
                               returnStdout: true,
                               script: 'git rev-parse HEAD'
                            )}"""
                BuildHashStoreFile = 'buildHashStore.txt'
                BuildHashHistory = 'none'                
            }
      steps {
        sh ' echo The Hash is: $CurrentCommitHash'   
        sh 'echo The Commit Count before increment: $CommitCount'
        
        script {
                    env.FILENAME = readFile 'output.txt'
                }
                echo "${env.FILENAME}"
        
        
        writeFile file: 'buildHashStore.txt', text: '$CurrentCommitHash'
        
        
        sh """
          if [ $BuildHashHistory != "none" ]; then
              echo There is A previous hash stored
            else
              echo There is NOT A previous hash stored
            fi
        """
      }
    }
  }
}
