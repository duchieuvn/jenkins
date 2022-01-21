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
          withDockerRegistry([ credentialsId: "dockerhub_id", url: "" ]){
            bat 'docker tag aa duchieuvn/aa'
            bat 'docker push duchieuvn/aa'
          }
        }
      }
  }
  
  post {
    always{
      bat 'docker logout' 
    }
  }
}
