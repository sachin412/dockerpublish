pipeline {
      environment {
    registry = "sachin41/test"
    registryCredential = '14121993'
        }
   agent any 
   stages {
  stage('Building image') {
    steps{
      script {
        docker.build registry + ":$BUILD_NUMBER"
         
       }
     }
  }     
   stage('push image') {
     steps{
        withDockerRegistry([ credentialsId: "$registryCredential", url: "https://registry.hub.docker.com/sachin41" ]) {
          sh  'docker push  sachin41/test:$BUILD_NUMBER'          
         } 
       }
     }
  
  
  
 }
}
