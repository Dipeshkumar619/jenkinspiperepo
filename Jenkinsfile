def nameOfPerson = "john"
def printName(name){
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