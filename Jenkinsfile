pipeline {
	agent any 
	stages {
		stage('Parallel Stage'){
			steps{
				echo 'Test stage'
				error 'Stage failed'
				script{
					currentBuild.result = 'UNSTABLE'

				}
			}
				

		}
	}
	post{
		unstable{
			echo "========Build is unstable========"
		}

		changed{
			echo "==========it run if build result different from previous run==="		}

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
