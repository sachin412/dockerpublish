pipeline {
   /*withCredentials([[$class: 'UsernamePasswordMultiBinding', credentialsId: params.JP_DockerMechIdCredential, usernameVariable: 'sachin41', passwordVariable: '14121993']]) {
	usr = sachin41
	pswd = 14121993
		} */
      environment {
    registry = "sachin41/myubuntuapache"
    registryCredential = '14121993'
        }
   agent any 
   stages {
  stage('Building image') {
    steps{
      script {
       def app = docker.build registry + ":$BUILD_NUMBER"
	      
       }
     }
  }     
 stage('Deploy Image') {
      steps{
        script {
          docker.withRegistry( 'https://hub.docker.com/sachin41', 'docker-hub' ) {
            dockerImage.push()
          }
        }
      }
    }
  
  
 }
}
