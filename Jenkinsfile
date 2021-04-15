pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        sh 'mvn install'
      }
    }

    stage('deploy') {
      steps {
        sh 'java -jar target/*.jar'
      }
    }

  }
}