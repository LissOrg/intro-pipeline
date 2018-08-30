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
            echo "${TEST_USER_USR}"
            echo "${TEST_USER_PSW}"
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
    TEST_USER = credentials('test-user')
  }
  parameters {
    string(name: 'Name', defaultValue: 'whoever you are', description: 'Who should I say hi to?')
  }
}