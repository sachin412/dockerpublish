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
        docker.build registry + ":$BUILD_NUMBER"
         
       }
     }
  }     
  stage('push image') {
     steps{ 
      withDockerRegistry([credentialsId: 'docker-hub', url: 'https://cloud.docker.com/u/sachin41/repository/docker/sachin41']) {
             
	      sh 'docker push sachin41/myubuntuapache:$BUILD_NUMBER)'    
  }
       }
     }
  
  
  
 }
}
