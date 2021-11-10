pipeline {
  agent any
  options {
    buildDiscarder(logRotator(numToKeepStr: '5'))
  }
  stages {
    stage('Build') {
      steps {
        echo $BRANCH_NAME 
      }
    }
    stage('cat readme') {
      when {
        branch "sd*"
          
      }
      steps{
        sh 'cat README.md'
      }}
  }
  post {
    always {
        junit(
          allowEmptyResults: true, 
          testResults: '**/build/test-results/test/*.xml'
        )
    }
  }
}
