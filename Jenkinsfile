pipeline {
  agent {label 'linux'}
  options {
    buildDiscarder(logRotator(numToKeepStr: '5'))
  }
  stages {
    stage('Build') {
      steps {
        println "GitCommit ${env.GIT_COMMIT}"
        println "GitBranch ${env.GIT_BRANCH}"
        println "workspace path ${env.WORKSPACE}"
        println "workspace@tmp path ${env.WORKSPACE_TMP}"
      }
    }
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