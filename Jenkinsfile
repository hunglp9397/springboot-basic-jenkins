pipeline {
	agent any

	environment {
		mavenHome = tool 'jenkins-maven'
	}

	tools {
		jdk 'java-11'
	}

	stages {
		stage('Build'){
			steps {
				bat "mvn clean install -DskipTests"
			}
		}
	}
}