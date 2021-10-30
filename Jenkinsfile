pipeline{
	agent any 
	stages{
		stage("Build"){
			
			steps{
			checkout([$class: 'GitSCM', 
			branches: [[name: '*/master']], 
			extensions: [], 
			userRemoteConfigs: [[credentialsId: 'githubapi', 
			url: 'https://github.com/Dipeshkumar619/simple_java_project.git']]])

				echo "========executing A========"
				script{
					withMaven(maven: 'MVN_3_6_3',mavenSettingConfig: '4be60908-9402-4644-9137-a5e83675af91',
					options: [junitPublisher(disabled: true), artifactsPublisher(disabled: true)]){
						sh "mvn -X clean install"
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