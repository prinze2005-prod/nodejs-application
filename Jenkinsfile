pipeline {
  agent any
  stages {
    stage('git clone') {
      steps {
        git(url: 'https://github.com/prinze2005-prod/nodejs-application', branch: 'master')
      }
    }

    stage('docker-build') {
      steps {
        sh 'docker rm -f nodeapp'
        sh 'docker build -t nodeapp .'
        sh 'docker tag nodeapp prinze2005/nodeapp .'
      }
    }

  }
}