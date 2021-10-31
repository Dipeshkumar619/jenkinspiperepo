pipeline{
	agent any 

	stages{
		stage("Build"){
			
			steps{

				// build(job: 'build_child_job', 
				// parameters: [[$class: "StringParameterValue", name: "DeployEnv",value: "developement Env"]])
				   build job: 'build_child_job',
				   parameters: [string(name: 'deployEnv', value: 'development Env')]
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