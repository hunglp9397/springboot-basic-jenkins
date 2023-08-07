pipeline {
    agent docker

    stages {
        stage('Build') {
            agent {
                docker {
                    image 'maven:3.8.4-openjdk-11' // Use an image with Maven and Java 11
                    args '-v $HOME/.m2:/root/.m2' // Mount the Maven local repository
                }
            }

            steps {
                script {
                    checkout scm // Checkout the source code from your version control system
                    sh 'mvn clean install' // Build the Spring project using Maven
                }
            }
        }


    }


}
