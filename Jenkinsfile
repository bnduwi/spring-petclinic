pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh ' echo GIT_COMMIT %GIT_COMMIT%'
        sh '[ -s /tmp/myfile.txt ] && echo "File not empty" || echo "File empty"'
      }
    }
  }
}
