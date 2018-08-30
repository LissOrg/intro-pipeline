pipeline {
  agent {
    label 'jdk9'
  }
  stages {
    stage('stage1') {
      parallel {
        stage('stage1') {
          steps {
            echo "Hello ${MY_NAME}!"
          }
        }
        stage('stage1Parallel') {
          steps {
            echo 'I am parallel'
            sh 'java -version'
          }
        }
      }
    }
  }
  environment {
    MY_NAME = 'Liss'
  }
}