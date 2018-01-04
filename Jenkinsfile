/*Jenkinsfile (Declarative Pipeline)*/

/* pipeline start */
pipeline {

/* agent section */
  agent {
			node {
			        label "jslave"
				 }		
		}
/* tool section */
  tools {
     maven 'maven339'
	 jdk 'jdk180'
	    }
/* Stage Section */		
  stages {
  
  stage ('Initialize'){
	  steps {
			 sh '''
				echo "PATH = $PATH"
				echo "M2_HOME = ${M2_HOME}"
				'''
			}
			}
		
  stage ('Verify Stage') {
	  steps {  
	  sh 'mvn clean verify'	 
			}  	   
		   }
	   
  stage ('Compile Stage') {
	  steps {
		sh 'mvn clean compile'
			}
		}
	
  stage ('Install Stage') {
	  steps {
		sh 'mvn clean install'
			}	  
		}
	
   }
}