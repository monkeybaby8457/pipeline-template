pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        git(url: 'https://gitscm.cisco.com/scm/csit/devops-portal-2.git', branch: 'master', credentialsId: '6ebf20cb-55ec-4263-b040-c70b339c7f1e')
      }
    }
  }
}