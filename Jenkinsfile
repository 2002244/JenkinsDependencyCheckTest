pipeline {
	agent any
	stages {
		stage('Checkout SCM') {
			steps {
				git '/home/Documents/SIT Y3T1/ICT3203 - Secure Software Development/week 6 - secure software design 2/JenkinsDependencyCheckTest'
			}
		}

		stage('OWASP DependencyCheck') {
			steps {
				dependencyCheck additionalArguments: '--format HTML --format XML --suppression suppression.xml', odcInstallation: 'Default'
			}
		}
	}	
	post {
		success {
			dependencyCheckPublisher pattern: 'dependency-check-report.xml'
		}
	}
}