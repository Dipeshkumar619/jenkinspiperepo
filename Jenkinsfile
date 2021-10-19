pipeline{
	agent any 
	
	stages{
	stage('Build'){
			when{
				changeRequest()
				//changelog '.*some_text.*'
			
			}
			
			steps{
				echo 'Hello World changelog'
			
			}
	
	}
	}


}
