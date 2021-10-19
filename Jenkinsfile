pipeline{
	agent any 
	
	stages{
	stage('Build'){
			when{
				//changeRequest()
				//changelog '.*some_text.*'
				when { changeset "**/*.js" }	
			}
			
			steps{
				echo 'Hello World changelog'
			
			}
	
	}
	}


}
