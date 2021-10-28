pipeline{
	agent{
		docker {
			image 'ubuntu:latest'
			customWorkspace '/home/ubuntu/customWorkspace'
		}
	}
/* 
	options{
		newContainerPerStage()
	} */
	stages{
		stage("Build"){
			steps{
				sh 'cat /etc/lsb-release'
				sh 'hostname'
			}
		}

		stage("Deploy"){
			steps{
				sh 'cat /etc/lsb-release'
				sh 'hostname'
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