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
     steps {
        withDockerRegistry([ credentialsId: "14121993", url: "" ]) {
          sh  'docker push  sachin41/test:$BUILD_NUMBER'          
        }
      }
  
  
  } 
 }
}
