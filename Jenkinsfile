pipeline {
  agent any
  stages {
    stage('Build') {
      agent {
        node {
          label 'master'
        }

      }
      steps {
        withMaven(maven: 'M3') {
          bat 'mvn clean install'
        }

      }
    }

    stage('Results') {
      steps {
        junit '**/target/surefire-reports/TEST-*.xml'
        archiveArtifacts 'target/*.jar'
      }
    }

  }
}