/*Jenkinsfile (Declarative Pipeline)*/

pipeline {
  agent {
			docker {
				   image 'maven:3-alpine'
				   args "-v /root/.m2:/root/.m2"
				 }			
		}
  tools {
     maven 'maven339'
	 jdk 'jdk180'
	    }
		
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