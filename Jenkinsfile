
pipeline {
    agent {
        docker {
            image 'maven:3.8.4-openjdk-11' // Use an image with Maven and Java 11
            args '-v $HOME/.m2:/root/.m2' // Mount the Maven local repository
        }
    }

    stages {


        stage('Build') {
            steps {
                sh 'mvn clean install' // Build the Java project using Maven
            }
        }


    }


}
