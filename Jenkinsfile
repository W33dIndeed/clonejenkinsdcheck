pipeline {
	agent any
	stages {
		stage('Checkout SCM') {
			steps {
				git branch: 'master', url:'https://github.com/W33dIndeed/clonejenkinsdcheck.git'
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
