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
	   stage('custom repo') {
	
		   steps{
		    
		   sh 'docker tag node localhost:5000/node1'
	           sh 'docker push localhost:5000/node1'		   
		   
		   }
		   
	   }
	   
 stage('Deploy Image') {
      steps{   
	      script {
	      docker.withRegistry('', 'docker-hub') {
           sh 'docker push $registry:$BUILD_NUMBER'         
	      }
	   }		      
      }
    }
  
  
 }
}
