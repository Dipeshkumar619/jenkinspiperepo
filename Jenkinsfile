pipeline{
	agent any
	stages{
		stage("A"){
			steps{
				echo "========executing A========"
				script{
					env.ENV_VAR1='JOHN'
					def GROOVY_VAR='SMITH'
					sh 'echo ENV_VAR1: $ENV_VAR1'
					echo "GROOVY_VAR: ${GROOVY_VAR}"
					sh 'echo ENV_VAR1: ${ENV_VAR1}'
					withEnv(['ENV_VAR2=Groovy','MVN_VERSION=mvn --version']){
							sh '$ENV_VAR2'
							sh '$MVN_VERSION'
							sh 'printenv'
					}
					sh 'echo ENV_VAR2: $ENV_VAR2'
					sh 'echo MVN_VERSION: $MVN_VERSION'
				}
			}

		}
		stage("B"){
			steps{
				script{
					env.shellStatus = sh(returnStatus: true, script: 'ls -a')
					echo "this is shellStatus is: $shellStatus"
				//	if(shellStatus != 0)
				//		currentBuild.result='FAILURE'

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