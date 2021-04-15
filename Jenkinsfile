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
        sh 'cp /home/vagrant/deployment.yml ./deployment-playbook.yml && cp /home/vagrant/Dockerfile ./ && ansible-playbook --user=vagrant deployment-playbook.yml ; rm deployment-playbook.yml ; rm Dockerfile'
      }
    }

  }
}