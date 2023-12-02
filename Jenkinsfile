pipeline {
//     agent any

     agent {
        docker {
            image 'maven:3.8.4' // Use the Maven Docker image with the desired version
//             args '-v /var/run/docker.sock:/var/run/docker.sock' // Mount Docker socket if needed
        }
    }


    environment {
        registry = "123497/springboot-basic-jenkins"
        IMAGE_NAME = "123497/springboot-basic-jenkins"
        TAG = "latest"
//         dockerImage = ''
    }





    stages {

         stage('Check Docker') {
                        steps {
                            sh 'docker --version'
                        }
                    }



//         stage('Initialize'){
//             steps {
//                 script {
//                     echo "Initialize"
//                     def dockerHome = tool 'myDocker'
//                     env.PATH = "${dockerHome}/bin:${env.PATH}"
//                 }
//             }
//         }
//
//         stage('Build Maven') {
//             steps {
//                echo "Building maven"
//                sh 'mvn clean install'
//                archiveArtifacts artifacts: '**/target/*.jar', allowEmptyArchive: true
//             }
//         }
//
//
//
//          stage('Build Docker images') {
//             agent any
//               steps {
//                 script {
//                        echo "Docker build"
//                        docker.withRegistry('https://registry.hub.docker.com') {
//                             def customImage = docker.build("${IMAGE_NAME}:${TAG}", ".")
//                        }
//
//                 }
//
//               }
//          }


    }




}
