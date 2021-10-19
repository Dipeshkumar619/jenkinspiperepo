pipeline{
	agent any 
	
	stages{
	stage('Build'){
			when{
				//changeRequest()
				//changelog '.*some_text.*'
				changeset glob: "*.js"
			
			}
			
			steps{
				echo 'Hello World changelog'
			
			}
	
	}
	}


}
