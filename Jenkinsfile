pipeline {
    agent {
            docker {
                image 'maven:3.8.4' // Use the Maven Docker image with the desired version
                args '-v /var/run/docker.sock:/var/run/docker.sock' // Mount Docker socket if needed
            }
        }

    stages {


        stage('Build') {
            steps {
               echo "Building"
               sh 'mvn clean install'
            }
        }

        stage('Test') {
            steps {
             echo "Testing"
            }
        }

        stage('Deploy') {
            steps {
              echo "Deploying 123"
            }
        }
    }


}
