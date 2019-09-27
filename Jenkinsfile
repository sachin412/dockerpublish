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
  /*stage('Building image') {
    steps{
      script {
       docker.build registry + ":$BUILD_NUMBER"
	      
       }
     }
  }     
	*/   stage('custom repo') {
	
		   steps{	
		   sh 'echo { "insecure-registries":["192.168.3.244:5000"] } > /etc/docker' 	   
		   sh 'docker tag node 192.168.3.244:5000/node22'
	           sh 'docker push 192.168.3.244:5000/node22'		   
		   
		   }
		   
	   }
	   
/* stage('Deploy Image') {
      steps{   
	      script {
	      docker.withRegistry('', 'docker-hub') {
           sh 'docker push $registry:$BUILD_NUMBER'         
	      }
	   }		      
      }
    } */
  
  
 }
}
