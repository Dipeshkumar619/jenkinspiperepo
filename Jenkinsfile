pipeline {
	agent any 
	stages {
		stage('Parallel Stage'){
			failFast true
			parallel {
				stage('A'){
					steps{
						echo 'Stage A'
						sleep 10
					}
				}
				stage('B'){
					steps{
						echo 'Stage B'
						sleep 10
						error 'failed stage'
					}
				}
				stage('C'){
					steps{
						echo 'Stage C'
						sleep 10
						
					}
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
