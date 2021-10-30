pipeline{
	agent any 
	stages{
		stage("Build"){
			checkout([$class: 'GitSCM', 
			branches: [[name: '*/master']], 
			extensions: [], 
			userRemoteConfigs: [[credentialsId: 'githubapi', 
			url: 'https://github.com/Dipeshkumar619/simple_java_project.git']]])

			steps{
				echo "========executing A========"
				script{
					withMaven(maven: 'maven_3_6_3'){
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