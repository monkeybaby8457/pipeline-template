pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        sh 'mvn --version'
        git(url: 'https://gitscm.cisco.com/scm/csit/devops-portal-2.git', branch: 'master', credentialsId: 'jqun')
      }
    }
  }
}