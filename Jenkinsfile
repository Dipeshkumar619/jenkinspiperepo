pipeline {
	agent any 
	stages {
		stage('Parallel Stage'){
			steps{
				echo 'Test stage'
				//error 'Stage failed'
				script{
					currentBuild.result = 'SUCCESS'

				}
			}
				

		}
	}
	post{

		aborted{
			echo "=========Pipeline is aborted!!============"
		}

		regression {
			echo "=======regression occured======="
		}

		unstable{
			echo "========Build is unstable========"
		}

		changed{
			echo "==========it run if build result different from previous run==="		
			}
		
		fixed{
			echo "the stage if fixed"
		}

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
