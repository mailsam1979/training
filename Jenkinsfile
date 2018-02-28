node 'slave' { 

   def gitBranch = 'master'
   def mvnHome = tool 'local_maven'			// ** local_maven configured in the global tool configuration.
   def jdkHome = tool 'local_jdk'			// ** local_jdk configured in the global tool configuration.
   
   stage('Stage1-Preparation') {       
      git url: 'https://github.com/mailsam1979/training.git', branch: "${gitBranch}"  		// get code from git                 
   }
   
   stage('Stage2-Maven Validate') {
      // Run the maven build
      if (isUnix()) {				// check if system is Unix Or not
         sh "${mvnHome}/bin/mvn clean verify"
      } else {
         bat(/"${mvnHome}\bin\mvn"  clean verify/)
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
   
   stage('Show-Output') {
       echo "Build number  ${BUILD_NUMBER} for Job ${PROJECT_NAME} is ${BUILD_STATUS}"
   }
}