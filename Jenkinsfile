pipeline {
    environment {
        registry = "123497/springboot-basic-jenkins"
//         registryCredential = 'dockerhub_id'
//         dockerImage = ''
    }
//
    agent {
            docker {
                image 'maven:3.8.4' // Use the Maven Docker image with the desired version
                args '-v /var/run/docker.sock:/var/run/docker.sock' // Mount Docker socket if needed
            }
        }

    stages {

        stage('Initialize'){
            steps {
                script {
                    echo "Initialize"
                    def dockerHome = tool 'myDocker'
                    env.PATH = "${dockerHome}/bin:${env.PATH}"
                }
            }
        }

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
                        echo "Docker build"
//                     dockerImage = docker.build registry  + ":latest"

                }

              }
         }


    }




}
