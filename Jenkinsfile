/*Jenkinsfile (Declarative Pipeline)*/
pipeline { 
  agent any
  environment {
      name = 'sukanta'
	          }
			   
  stages {
    stage ('Maven Build') {
	   steps { 
	      echo "Maven Build Starts and Ends"
		  echo "Name is ... ${env.name}"
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
   stage ('Set Env Vars surname ...') {
       environment {
	      surname = 'sahoo'
		     }
	   steps { 
	      echo "Show Env Var surname .... ${env.surname}"
          echo "###########################"
		     }
    stage ('Display all env vars') {
	    steps {
		   echo "List all Environment Variables"
		   sh 'printenv'
	   }

    }
}