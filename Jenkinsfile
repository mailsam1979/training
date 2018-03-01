node {
  def gitBranch = 'testing'
  def mvnHome = tool 'local_maven'
  def jdkHome = tool 'local_jdk'
  
  stage ('Checkout SCM'){
  git url: 'https://github.com/mailsam1979/training.git', branch: "${gitBranch}"
  //stash name: 'source', include: 'pom.xml,src/,Jenkinsfile'
  }
  
  stage('Code Build') {      
	  env.PATH = "${mvnHome}/bin:${env.PATH}"
	  
      if (isUnix()) {				
         sh 'mvn -Dmaven.test.failure.ignore clean install'
      } else {
         bat(/"${mvnHome}\bin\mvn" -Dmaven.test.failure.ignore clean install/)
      }
   }
}