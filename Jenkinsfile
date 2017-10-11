/*Jenkinsfile (Declarative Pipeline)*/
pipeline { 
  agent any
  environment {
      name = 'sukanta'
	  midname = 'kumar'
	          }
  parameters {
        string(name: 'Greeting1', defaultValue: 'Hello1', description: 'How should I greet the world?')
		string(name: 'Greeting2', defaultValue: 'Hello2', description: 'How should I greet the world?')
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
		}
    stage ('Display user defined Parameters1') {
	    steps {
		   echo "${params.Greeting1} ... Vikram"
	          }
	   }
    stage ('Display user defined Parameters2') {
	    steps {
		   echo "${params.Greeting2} ... Vikram"
	          }
	   }
		   
    } 
    post {
      always {
        mail to: sukanta04u@gmail.com, subject: 'pipeline passed'
             }
      failed {
        mail to: sukanta04u@gmail.com, subject: 'pipeline failed'
             }
         }			 
}