pipeline{
	agent any 

	stages{
		stage("Build"){
			
			steps{

				// def buildJobReturnValue = build job: 'build_child_job', 
				// parameters: [[$class: "StringParameterValue", name: "deployEnv", value: "development env"]]

				// build(job: 'build_child_job', 
				// parameters: [[$class: "StringParameterValue", name: "DeployEnv",value: "developement Env"]])
				script {
				def buildJobReturnValue =  build propagate: false, job: 'build_child_job', parameters: [string(name: 'deployEnv', value: 'Production')]
				echo "buildJobReturnValue.result: ${buildJobReturnValue.result}"

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