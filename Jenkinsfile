pipeline {
  agent any
  environment{
   CommitCount = 0 
  }
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
        
        writeFile file: 'buildHashStore.txt', text: 'Working with files the Groovy way is easy.'
        sh 'ls -l buildHashStore.txt'
        sh 'cat buildHashStore.txt'
        
        sh 'echo The workspace is ${env.WORKSPACE}'
        
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
