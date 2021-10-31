pipeline{
	agent any 
	stages{
		stage("Build"){
			
			steps{
				checkout([$class: 'GitSCM', 
				branches: [[name: '*/master']], 
				extensions: [], 
				userRemoteConfigs: [[credentialsId: 'githubapi', 
				url: 'https://github.com/Dipeshkumar619/simple_java_project_with_jacoco.git']]])

				echo "========executing A========"
				script{
					withMaven(maven: 'MVN_3_6_3',mavenSettingConfig: '4be60908-9402-4644-9137-a5e83675af91',
					options: [junitPublisher(disabled: false), artifactsPublisher(disabled: false)]){
						sh "mvn clean install"
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