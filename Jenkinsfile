pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        sh 'mvn install'
      }
    }

    stage('test') {
      steps {
        sh 'mvn sonar:sonar -Dsonar.projectKey=org.springframework.samples:spring-petclinic -Dsonar.host.url=http://localhost:9000 -Dsonar.login=6c5e71dc7901ad10acd7a87023e4d7ba69041d2c'
      }
    }

    stage('deploy') {
      steps {
        sh 'java -jar target/*.jar'
      }
    }

  }
}