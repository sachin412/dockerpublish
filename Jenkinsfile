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
         docker push   
       }
     }
   } 
 }
}
