
//this is scripted syntax, works without defining stages too. other approach is declarative syntax


/*node {
	echo "Build"
	echo "Test"
	echo "Test"
}	*/


//Declarative 


pipeline {
	agent any
	stages {
		stage('Build'){
			steps {
				echo "Build"
			}
		}
		stage('Test'){
			steps {
				echo "Test"
			}
		}
		stage('Integration Test'){
			steps {
				echo "Integration Test"
			}
		}
	}
}

