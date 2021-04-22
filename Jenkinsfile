pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh 'mvm clean compile'
      }
    }

    stage('Unit test') {
      steps {
        sh '''mvm test
junit \'**/target/surefire-reports/TEST-*.xml\''''
      }
    }

    stage('Publish') {
      steps {
        sh '''mvm package
archive \'target/*.jar\''''
      }
    }

  }
}