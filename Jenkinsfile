pipeline{
	agent none

	stages{
		stage('Checkout'){
			agent any 
			steps{
				checkout([$class: 'GitSCM', 
				branches: [[name: 'dockerfile']], 
				extensions: [], 
				userRemoteConfigs: [[credentialsId: 'githubapi', url: 'https://github.com/Dipeshkumar619/jenkinspiperepo.git']]])
			}
		}


		stage("Build"){
			agent{
				dockerfile true
			}
			steps{
				sh '''
				#!bin/bash
				curl https://www.google.com/
				cat /etc/redhat-release'''
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