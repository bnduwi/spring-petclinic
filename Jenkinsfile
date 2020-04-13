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
            }
      steps {
        sh ' echo The Hash is: $CurrentCommitHash'
        sh 'echo $CurrentCommitHash > "buildHashStore.txt" '
        sh ' echo The Hash File is: $BuildHashStoreFile'
        sh """
            if [ -f buildHashStore.txt ]
            then
                if [ -s buildHashStore.txt ]
                then
                    echo "File exists and not empty"
                else
                    echo "File exists but empty"
                fi
            else
              echo "File not exists"
            fi
        """
      }
    }
  }
}
