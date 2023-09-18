
//this is scripted syntax, works without defining stages too. other approach is declarative syntax


/*node {
	echo "Build"
	echo "Test"
	echo "Test"
}	*/


//Declarative 


pipeline {
	//agent any
	agent { docker{ image 'maven:3.6.3'}}
	stages {
		stage('Build'){
			steps {
				sh 'mvn --version'
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
	post {
		always {                          //multiple options. Other options changed, unstable
			echo 'I am awesome. i run always'  
		}
		success {
			echo 'I run when its successful'
		}
		failure { 
			echo 'I run when you fail'
		}	
		changed { 
			echo 'I run whenever status of build changes'
		}	
	}
}

