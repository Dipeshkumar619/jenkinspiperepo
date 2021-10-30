pipeline{
	agent any
	stages{
		stage("A"){
			steps{
				echo "========executing A========"
				script{
					def shellOutput = sh(returnStdout: true, script: 'ls -a').trim()
					echo "this is shellOutput is: ${shellOutput}"
				}
			}

		}
		stage("B"){
			steps{
				script{
					def shellStatus = sh(returnStatus: true, script: 'ls -a')
					echo "this is shellStatus is: ${shellStatus}"

				}
			}
		}
		stage("C"){
			steps{
				script{
					def returnValue = sh(returnStatus: true, returnStdout: true, script: 'ls -a')
					echo "this is returnValue is: ${returnValue}"
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