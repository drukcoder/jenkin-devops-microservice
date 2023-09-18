
//this is scripted syntax, works without defining stages too. other approach is declarative syntax


/*node {
	echo "Build"
	echo "Test"
	echo "Test"
}	*/


//Declarative 


pipeline {
	agent any  // using any as agent, left to jenkins 
	//agent { docker { image 'node:13.8' }} //using node.js as agent,version from docker node runner 
	//agent { docker{ image 'maven:3.6.3'}}
	/*environment {
		dockerHome = tool 'myDocker'
		mavenHome = tool 'myMaven'
		PATH = "$dockerHome/bin:$mavenHome/bin:$PATH"
	}*/
	
	stages {
		stage('Build'){
			steps {
				sh 'docker version'    
				sh 'mvn --version'
				echo "Build"
				echo "PATH - $PATH"
				echo "BUILD_NUMBER - $env.BUILD_NUMBER"
				echo "BUILD_ID - $env.BUILD_ID"
				echo "JOB_NAME - $env.JOB_NAME"
				echo "BUILD_TAG - $env.BUILD_TAG"
				echo "BUILD_URL - $env.BUILD_URL"
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

