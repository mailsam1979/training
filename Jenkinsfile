/*Jenkinsfile (Declarative Pipeline)*/

pipeline {
  agent any
  tools {
     maven 'local_maven'
	 jdk 'local_jdk'
	    }
		
  stages {
  
  stage ('Initialise'){
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
    sh 'mvn clean Install'
		}
	}
	
   }
}