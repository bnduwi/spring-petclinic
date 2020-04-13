pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh ' git rev-parse HEAD'
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
