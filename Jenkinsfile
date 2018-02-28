node('slave') {
   input 'Ready to go?'   
   def gitBranch = 'master'
   def mvnHome = tool 'local_maven'
   def jdkHome = tool 'local_jdk'
   
   // if project is parameterized 
   
   println"The Value for to_run is ${params.to_run}"
   
   if (params.to_run == 'yes') {
   
   stage('Stage1-Preparation') {       
      git url: 'https://github.com/mailsam1979/training.git', branch: "${gitBranch}"                 
   }
   
   stage('Stage2-Maven Validate') {
      // Run the maven validate
      if (isUnix()) {				// check if system is Unix Or not
         sh "${mvnHome}/bin/mvn clean validate"
      } else {
         bat(/"${mvnHome}\bin\mvn"  clean validate/)
      }
   }   
   
   stage('Stage3-Maven Install') {      
	  env.PATH = "${mvnHome}/bin:${env.PATH}"			// add mvn path to PATH and use mvn directly
	  
      if (isUnix()) {				
         sh 'mvn -Dmaven.test.failure.ignore clean install'
      } else {
         bat(/"${mvnHome}\bin\mvn" -Dmaven.test.failure.ignore clean install/)
      }
   }
   
   stage('Test-Results') {
     junit '**/target/surefire-reports/TEST-*.xml'
     archive 'target/*.jar'
   }
   
   stage('Show-Output') {						// use of Jenkins BUilt-in variables in groovy scripting
	   println"Job Name  ${env.JOB_NAME}"
       println"Build number  ${env.BUILD_NUMBER}"	   
	   println"Build URL ${env.BUILD_URL}"
	   println"Jenkins Node ${env.NODE_NAME}"
	   println"Jenkins URL ${env.JENKINS_URL}"
	
   }
  }
}