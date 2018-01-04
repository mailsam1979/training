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
		sh 'mvn clean install -Dmaven.test.failure.ignore=true'
			}
		}
		
  postBuild {
			always {
						archive "target/*.jar"
						junit 'target/surefire-reports/*.xml'
					}
			}
  notifications {  
			success {
					slackSend (color: 'GREEN', message: "Job: '${env.JOB_NAME} [${env.BUILD_NUMBER}]' (${env.BUILD_URL}) SUCCESSFUL ")					
					}
			unstable {
					slackSend (color: 'YELLOW', message: "Job: '${env.JOB_NAME} [${env.BUILD_NUMBER}]' (${env.BUILD_URL}) Unstable ")					
					}							
			failure {
					slackSend (color: 'RED', message: "Job:  '${env.JOB_NAME} [${env.BUILD_NUMBER}]' (${env.BUILD_URL})  Failed")					
					}	            	  
		}
	
   }
}