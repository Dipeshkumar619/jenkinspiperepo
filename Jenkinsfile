pipeline{
	agent{
		docker {
			image 'quay.io/dipesh_gupta_ak/myfirstrepo:latest'
			registryUrl 'https://quay.io'
			registryCredentialId 'dipesh_gupta_ak'
		}
	}

	stages{
		stage("Build"){
			steps{
				sh 'printenv'
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