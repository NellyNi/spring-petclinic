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
        sh 'ls'
      }
    }

    stage('deploy') {
      steps {
        sh 'cp /home/vagrant/playbook.yml ./playbook.yml && cp /home/vagrant/Dockerfile ./ && ansible-playbook --user=vagrant playbook.yml ; rm playbook.yml ; rm Dockerfile'
      }
    }

  }
}