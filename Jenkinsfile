/*Jenkinsfile (Declarative Pipeline)*/

pipeline {
  agent any
  tools {
     maven 'local_maven'
	 jdk 'local_jdk'
	    }
		
  stages {
  stage {
  steps {
	     sh '''
		    echo "PATH = $PATH"
			echo "M2_HOME = ${M2_HOME}"
			'''
			}
		}
  stage ('Veryfy Stage') {
  steps {
  dir("project_templates/java_project_template")   
  sh 'mvn clean verify'	 
	      }  	   
       }
  
   }
}