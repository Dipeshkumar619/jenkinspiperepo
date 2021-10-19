pipeline{
	agent any 
	
	stages{
	stage('Build'){
			when{
				//changeRequest()
				//changelog '.*some_text.*'
				changeset "**/*.js"	
			}
			
			steps{
				echo 'Hello World changelog'
			
			}
	
	}
	}


}
