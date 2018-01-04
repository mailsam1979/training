/*Jenkinsfile (Declarative Pipeline)*/

/* pipeline start */
pipeline {

/* agent section */
  agent {
			node {
			        label "kslave"
				 }		
		}
/* tool section */
  tools {
     maven 'maven339'
	 jdk 'jdk180'
	    }
/* Stage Section */		
  stages {	
  stage ('Install Stage') {
	  steps {
		sh 'mvn clean install'
			}
      post {
			always {
						archive "target/*.jar"
						junit 'target/surefire-reports/*.xml'
					}
			success {
					slackSend (color: '#FFFF00', message: "STARTED: Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]' (${env.BUILD_URL})")					
					}
			unstable {
					slackSend (color: '#FFFF00', message: "STARTED: Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]' (${env.BUILD_URL})")					
					}							
			failure {
					slackSend (color: '#FFFF00', message: "STARTED: Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]' (${env.BUILD_URL})")					
					}	            	  
		}
	
   }
}
}