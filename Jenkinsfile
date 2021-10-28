def nameOfPerson = "john"
def printName(){
	echo name
}
pipeline{
	agent any

	stages{
		stage('Checkout'){
			steps{
				script{
					printName(nameOfPerson)
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