pipeline {
	agent any
	stages {
		stage('Checkout SCM') {
			steps {
				git url: 'file:///C:/Users/Louis/OneDrive/Desktop/Y2T3/2216SSD/Lab/JenkinsDependencyCheckTest', branch: 'master'
			}
		}

		stage('OWASP DependencyCheck') {
			steps {
				dependencyCheck additionalArguments: '--format HTML --format XML', odcInstallation: 'Default'
			}
		}
	}	
	post {
		success {
			dependencyCheckPublisher pattern: 'dependency-check-report.xml'
		}
	}
}