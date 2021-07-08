pipeline {
  agent {
    node {
      label 'master'
    }

  }
  stages {
    stage('Build') {
      agent {
        node {
          label 'master'
        }

      }
      steps {
        withMaven(jdk: 'Jdk', maven: 'M3') {
          bat 'mvn clean install'
        }

      }
    }

    stage('Results') {
      agent {
        node {
          label 'master'
        }

      }
      steps {
        junit '**/target/surefire-reports/TEST-*.xml'
        archiveArtifacts 'target/*.jar'
      }
    }

  }
}