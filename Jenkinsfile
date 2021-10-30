pipeline{
	agent{
		label "node"
	}
	stages{
		stage("A"){
			steps{
				echo "========executing A========"
				script{
					def shellOutput = sh(returnStdout: true, script: 'll -a')
					echo "this is shellOutput is: ${shellOutput}"
				}
			}

		}
		stage("B"){
			steps{
				script{
					def shellStatus = sh(returnStatus: true, script: 'll -a')
					echo "this is shellStatus is: ${shellStatus}"

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