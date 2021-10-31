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
					options: [junitPublisher(disabled: false), artifactsPublisher(disabled: true)]){
						sh "mvn -X clean install"
						jacoco buildOverBuild: true, changeBuildStatus: true, deltaBranchCoverage: '40', deltaClassCoverage: '40', deltaComplexityCoverage: '40', deltaInstructionCoverage: '40', deltaLineCoverage: '40', deltaMethodCoverage: '40', maximumMethodCoverage: '75', minimumMethodCoverage: '50'
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