pipeline {
  node {
     checkout scm
	 }
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

    }
}