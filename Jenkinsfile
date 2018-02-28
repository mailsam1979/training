node ('slave') {
        
   label 'slave'
   def gitBranch = 'master'
   def mvnHome = tool 'local_maven'			// ** local_maven configured in the global tool configuration.
   def jdkHome = tool 'local_jdk'			// ** local_jdk configured in the global tool configuration.
   
   stage('Preparation') { 
      // for display purposes
      // Get some code from a GitHub repository
      git url: 'https://github.com/mailsam1979/training.git', branch: "${gitBranch}"
                
      
   }
   stage('Build1') {
      // Run the maven build
      if (isUnix()) {				// check if system is Unix Or not
         sh "'${mvnHome}/bin/mvn' -Dmaven.test.failure.ignore clean package"
      } else {
         bat(/"${mvnHome}\bin\mvn" -Dmaven.test.failure.ignore clean package/)
      }
   }
   
   stage('Build2') {
      // add mvn path to PATH and use mvn directly
	  env.PATH = "${mvnHome}/bin:${env.PATH}"
	  
      if (isUnix()) {				
         sh 'mvn -Dmaven.test.failure.ignore clean package'
      } else {
         bat(/"${mvnHome}\bin\mvn" -Dmaven.test.failure.ignore clean package/)
      }
   }
   stage('Results') {
     junit '**/target/surefire-reports/TEST-*.xml'
     archive 'target/*.jar'
   }
}