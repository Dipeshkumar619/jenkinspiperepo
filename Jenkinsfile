pipeline {
	agent any 
	stages {
		stage('Parallel Stage'){
			steps{
				echo 'Test stage'
		//  error 'Stage failed'
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
