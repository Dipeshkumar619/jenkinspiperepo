pipeline{
	agent any 
	stages{
		stage("Build"){
			
			steps{
				checkout([$class: 'GitSCM', 
				branches: [[name: '*/master']], 
				extensions: [], 
				userRemoteConfigs: [[credentialsId: 'githubapi', 
				url: 'https://github.com/Dipeshkumar619/simple_java_project_with_sonarqube.git']]])

				echo "========executing A========"
				script{
					withMaven(maven: 'MVN_3_6_3'){
						sh "mvn clean install"
					}

					withSonarQubeEnv('sonarqube'){
						sh 'mvn sonar:sonar'
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