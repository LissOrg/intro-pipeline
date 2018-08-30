pipeline {
  agent {
    label 'jdk9'
  }
  stages {
    stage('stage1') {
      parallel {
        stage('stage2') {
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
    stage('Deploy') {
      options {
        timeout(time: 30, unit: 'SECONDS')
      }
      input {
        message 'Should we continue?'
      }
      steps {
        echo 'Continuing with deployment'
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