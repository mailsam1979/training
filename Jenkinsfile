node {
  def gitBranch = 'master'
  def mvnHome = tool 'local_maven'
  def jdkHome = tool 'local_jdk'
  
  stage ('Checkout SCM'){
  git url: 'https://github.com/mailsam1979/training.git'
  }
  
  stage('Code Build') {      
	  env.PATH = "${mvnHome}/bin:${env.PATH}"
	  
      if (isUnix()) {				
         sh 'mvn -Dmaven.test.failure.ignore clean install'
      } else {
         bat(/"${mvnHome}\bin\mvn" -Dmaven.test.failure.ignore clean install)
      }
   }
  
  def version = getversion()		// get value form getversion() function
  if (version) {
	echo "Build Version is ${version}"
	}
  def getversion() {
	def matcher = readFile('pom.xml') =~ '<version>(.+)</version>'
	matcher ? matcher[0][1] : null
	}
}