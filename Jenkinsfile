/*Jenkinsfile (Declarative Pipeline)*/
pipeline { 
  agent any
    }
	
  tools {
     maven 'local_maven'
     jdk 'local_jdk'
        }
		
  stages {
    stage ('Initialise') {
	   steps { 
	      sh '''
		       echo "JAVA_HOME = ${local_jdk}"
			   echo "M2_HOME = ${local_maven}"
			  '''
		     }
	   }
    stage ('Final') {
	   steps { 
	      echo "THis sia minimal pipeline"  
		     }
	   }
   	   
    } 
}