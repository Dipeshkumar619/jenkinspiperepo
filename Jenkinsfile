pipeline{
	agent any 
	parameters{
		string(name: 'deployEnv', description: 'deployment environment variable')
	}
	stages{
		stage("Build"){
			
			steps{

				script{

					echo "child job1 input param deployEnv: ${params.deployEnv}"
					echo "child job1 input param deployEnv: ${deployEnv}"
					currentBuild.result='FAILURE'


				}
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