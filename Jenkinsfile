pipeline {
  agent any
  environment{
    DOCKERHUB_CREDENTIALS = credentials('dockerhub_id')  
  }
  stages {
      stage('Build') {
        steps {
          bat 'docker build -t aa .'
        }
      }
    
      stage('Push Image') {
        steps {                
          bat 'echo $DOCKERHUB_CREDENTIALS_PSW | docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin'
          bat 'docker push aa'
        }
      }
  }
  
  post {
    always{
      bat 'docker logout' 
    }
  }
}
