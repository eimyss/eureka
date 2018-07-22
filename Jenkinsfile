pipeline {
  agent any
  stages {
    stage('checkout') {
      steps {
        echo 'test'
      }
    }
    stage('build') {
      steps {
        sh 'mvn clean package'
      }
    }
    stage('archive') {
      steps {
        junit(allowEmptyResults: true, testResults: 'test.xml')
      }
    }
    stage('docker create') {
      steps {
        sh 'docker build .'
      }
    }
  }
}