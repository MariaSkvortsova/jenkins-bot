pipeline {
  agent any
  stages {
    stage('unit tests') {
      steps {
        sh 'echo \'unit tests...\''
      }
    }
    stage('integration') {
      parallel {
        stage('integration') {
          steps {
            sh 'echo \'integration\''
          }
        }
        stage('ui') {
          steps {
            build(job: 'UI_tests', propagate: true, wait: true)
            sh 'echo "Test"'
          }
        }
      }
    }
    stage('deploy') {
      steps {
        sh 'echo \'deploy\''
      }
    }
  }
}