pipeline {
    agent {
            docker {
                image 'maven:3.8.4' // Use the Maven Docker image with the desired version
                args '-v /var/run/docker.sock:/var/run/docker.sock' // Mount Docker socket if needed
            }
        }

    stages {


        stage('Build Maven') {
            steps {
               echo "Building"
               sh 'mvn clean install'
               archiveArtifacts artifacts: '**/target/*.jar', allowEmptyArchive: true
            }
        }



         stage('Docker Build') {
            agent any
              steps {
                script {
                    sh 'docker build -t 123497/springboot-basic-jenkins .'
                }

              }
         }


    }




}
