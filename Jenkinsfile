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
        sh "rm ${env.WORKSPACE}/this_will_be_deleted"
        sh "touch ${env.WORKSPACE}/new_file"
        sh "echo hello >> README.md"
        sh "git clone ${env.WORKSPACE} ${env.WORKSPACE_TMP}/GitleaksDir"
        sh "git branch ${env.WORKSPACE_TMP}/GitleaksDir"
      }
    }
  }
}