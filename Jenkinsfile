pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        bat 'docker build -t $BUILD_NUMBER .'
      }
    }

  }
}
