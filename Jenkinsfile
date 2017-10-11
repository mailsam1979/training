pipeline { 
  agent any
  stages {
    stage ('Maven Build') {
	   steps { 
	      echo "Maven Build Starts and Ends"
		  echo "###########################"
		     }
	   }
    stage ('Maven Compile') {
	   steps { 
	      echo "Maven Compile Starts and Ends"
          echo "###########################"		  
		     }
	   }
    stage ('Maven TEst') {
	   steps { 
	      echo "Maven Test Starts and Ends"
          echo "###########################"
		     }
	   }
    stage ('Show BuildID') {
	   steps { 
	      echo "Build is ${env.BUILD_ID}"
          echo "###########################"
		     }
	   }
	   
    stage ('Show Jenkins JOb & HOme Dir Name') {
	   step1 { 
	      echo "Jenkins Job Name is ${env.JOB_NAME}"
          echo "##################################"
		     }
	   step2 { 
	      echo "Jenkins Job Name is ${env.HOME}"
          echo "#####################################"
		     }
	   }
 
    }
}