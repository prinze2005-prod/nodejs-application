pipeline {
  agent any
  stages {
    stage('git clone') {
      steps {
        git(url: 'https://github.com/prinze2005-prod/nodejs-application', branch: 'master')
      }
    }

    stage('build') {
      steps {
        sh '''docker rm -f prinze2005/nodeapp 
docker build -t nodeapp .
docker tag nodeapp prinze2005/nodeapp '''
      }
    }

    stage('docker login') {
      environment {
        DOCKERHUB_USER = 'prinze2005'
        DOCKERHUB_PASSWORD = 'dckr_pat_VUs5_D7Y6TNknbEyHhIDAqcGSsU'
      }
      steps {
        sh 'docker login -u  $DOCKERHUB_USER -p  $DOCKERHUB_PASSWORD'
      }
    }

  }
}