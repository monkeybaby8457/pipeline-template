pipeline {
  agent any
  stages {
    stage('checkout') {
      steps {
        sh 'git config --system core.longpaths true'
        git(credentialsId: '0cca2a62-8d55-4a0b-a4d4-e49f60d9393b', url: 'https://gitscm.cisco.com/scm/~jqun/portal2.git', branch: 'master', changelog: true, poll: true)
      }
    }
    stage('compile') {
      steps {
        parallel(
          "compile Api-gateway": {
            sh '''






mvn -e -file Api-gateway/pom.xml clean -P prod org.jacoco:jacoco-maven-plugin:prepare-agent install'''
            
          },
          "compile App-service": {
            sh 'mvn -e -file App-service/pom.xml clean -P prod org.jacoco:jacoco-maven-plugin:prepare-agent install'
            
          },
          "compile App_module_jenkins-service": {
            sh 'mvn -e -file App_module_jenkins-service/pom.xml clean -P prod org.jacoco:jacoco-maven-plugin:prepare-agent install'
            
          },
          "compile App_module_udeploy-service": {
            sh 'mvn -e -file App_module_udeploy-service/pom.xml clean -P prod org.jacoco:jacoco-maven-plugin:prepare-agent install'
            
          },
          "compile Config-server": {
            sh 'mvn -e -file Config-server/pom.xml clean -P prod org.jacoco:jacoco-maven-plugin:prepare-agent install'
            
          },
          "compile Core-service": {
            sh 'mvn -e -file Core-service/pom.xml clean -P prod org.jacoco:jacoco-maven-plugin:prepare-agent install'
            
          },
          "compile Mail-service": {
            sh 'mvn -e -file Mail-service/pom.xml clean -P prod org.jacoco:jacoco-maven-plugin:prepare-agent install'
            
          },
          "compile Metrics_module_appdynamics-service": {
            sh 'mvn -e -file Metrics_module_appdynamics-service/pom.xml clean -P prod org.jacoco:jacoco-maven-plugin:prepare-agent install'
            
          },
          "compile Metrics_module_bitbucket-service": {
            sh 'mvn -e -file Metrics_module_bitbucket-service/pom.xml clean -P prod org.jacoco:jacoco-maven-plugin:prepare-agent install'
            
          },
          "compile Metrics_module_rally-service": {
            sh 'mvn -e -file Metrics_module_rally-service/pom.xml clean -P prod org.jacoco:jacoco-maven-plugin:prepare-agent install'
            
          },
          "compile Metrics_module_sonar-service": {
            sh 'mvn -e -file Metrics_module_sonar-service/pom.xml clean -P prod org.jacoco:jacoco-maven-plugin:prepare-agent install'
            
          },
          "compile Metrics_module_tareport-service": {
            sh 'mvn -e -file Metrics_module_tareport-service/pom.xml clean -P prod org.jacoco:jacoco-maven-plugin:prepare-agent install'
            
          },
          "compile Registry-server": {
            sh 'mvn -e -file Registry-server/pom.xml clean -P prod org.jacoco:jacoco-maven-plugin:prepare-agent install'
            
          },
          "compile Remedy-service": {
            sh 'mvn -e -file Remedy-service/pom.xml clean -P prod org.jacoco:jacoco-maven-plugin:prepare-agent install'
            
          },
          "compile UI": {
            sh 'mvn -e -file UI/pom.xml clean -P prod org.jacoco:jacoco-maven-plugin:prepare-agent install'
            
          }
        )
      }
    }
  }
}