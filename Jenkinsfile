pipeline {
  agent any
  stages {
    stage('stage1') {
      parallel {
        stage('stage1') {
          steps {
            echo 'Hello World!'
          }
        }
        stage('stage1Parallel') {
          steps {
            echo 'I am parallel'
          }
        }
      }
    }
  }
}