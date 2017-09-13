pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        sh 'git config --system core.longpaths true'
        git(credentialsId: '0cca2a62-8d55-4a0b-a4d4-e49f60d9393b', url: 'https://gitscm.cisco.com/scm/~jqun/portal2.git', branch: 'master', changelog: true, poll: true)
      }
    }
  }
}