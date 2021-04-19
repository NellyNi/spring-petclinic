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
        sh 'mvn sonar:sonar -Dsonar.projectKey=org.springframework.samples:spring-petclinic -Dsonar.host.url=http://localhost:9000 -Dsonar.login=e7a90af626a0576e8b3c6d2b042a0c9e5668e921'
      }
    }

    stage('deploy') {
      steps {
        sh 'cp /home/vagrant/deployment.yml ./deployment-playbook.yml && cp /home/vagrant/Dockerfile ./ && ansible-playbook --user=vagrant deployment-playbook.yml ; rm deployment-playbook.yml ; rm Dockerfile'
      }
    }

  }
}