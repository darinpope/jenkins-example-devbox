pipeline {
  agent any
  stages {
    stage('verify devbox installation') {
      steps {
        sh 'devbox version'
      }
    }
    stage("verify tool installation on agent") {
      steps {
        sh '''
          java -version
          mvn --version || exit 0
        '''
      }
    }
    stage('verify tool installation in devbox') {
      steps {
        sh 'devbox run verify'
      }
    }
    stage('build the app') {
      steps {
        sh 'devbox run build'
      }
    }
  }
}