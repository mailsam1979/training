/*Jenkinsfile (Declarative Pipeline)*/

pipeline {
  agent any
  stages {
    stage ('Compile Stage') {
	   steps {
           withMaven (maven : 'local_maven')
             sh 'mvn clean compile'	 
	      }  	   
       } 
   }
}