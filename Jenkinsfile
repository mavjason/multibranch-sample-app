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
        println scm
        println scm.GIT_URL
        println scm.GIT_BRANCH
        println scm.GIT_COMMIT
        println "workspace path ${env.WORKSPACE}"
        println "workspace@tmp path ${env.WORKSPACE_TMP}"
        sh "rm ${env.WORKSPACE}/this_will_be_deleted"
        sh "touch ${env.WORKSPACE}/new_file"
        sh "echo hello >> README.md"
      }
    }
  }
}