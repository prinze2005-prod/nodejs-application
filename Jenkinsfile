pipeline {
  agent any
  stages {
    stage('git clone') {
      steps {
        git(url: 'https://github.com/prinze2005-prod/nodejs-application', branch: 'master')
      }
    }

    stage('') {
      steps {
        sh 'docker build -t nodeapp .'
      }
    }

  }
}