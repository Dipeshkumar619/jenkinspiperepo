pipeline{
	agent{
		docker {
			image 'maven:3.5.3-jdk-10-slim'
		}
	}

	stages{
		stage("Build"){
			agent{
				dockerfile true
			}
			steps{
				sh 'cat /etc/lsb-release'
			}
		}
	}	

	post{
		always{
			echo "========always========"
		}
		success{
			echo "========pipeline executed successfully ========"
		}
		failure{
			echo "========pipeline execution failed========"
		}
	}
}