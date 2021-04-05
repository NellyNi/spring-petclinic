pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        sh 'man install'
      }
    }

    stage('test') {
      steps {
        sh '''mvn sonar:sonar \\
>   -Dsonar.projectKey=org.springframework.samples:spring-petclinic \\
>   -Dsonar.host.url=http://localhost:9000 \\
>   -Dsonar.login=291cdd7adb7391e9ba26db2378be73882f09cfef'''
      }
    }

    stage('deploy') {
      steps {
        sh 'java -jar target/*.jar'
      }
    }

  }
}