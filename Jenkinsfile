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

  }
}