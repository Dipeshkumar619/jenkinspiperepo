pipeline{
	agent any 
	
	stages{
	stage('Build'){
			when{
				//changeRequest()
				//changelog '.*some_text.*'
				changeset pattern: "*.js", caseSensitive: true	
			}
			
			steps{
				echo 'Hello World changelog'
			
			}
	
	}
	}


}
