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
        sh '$CommitCount=$((CommitCount+1))'
        sh 'echo The Commit Count after increment: $CommitCount'
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
