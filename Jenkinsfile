pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        git(url: 'https://gitscm.cisco.com/scm/csit/devops-portal-2.git', branch: 'master', credentialsId: '0cca2a62-8d55-4a0b-a4d4-e49f60d9393b')
      }
    }
  }
}