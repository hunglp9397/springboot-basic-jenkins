pipeline {
    agent any

    environment {
        MAVEN_HOME = tool 'Maven'
    }

    stages {


        stage('Build') {
            steps {
                script {
                    def mvnCmd = "${env.MAVEN_HOME}/bin/mvn"
                    sh "${mvnCmd} clean install"
                }
            }
        }



        stage('Package') {
            steps {
                script {
                    def mvnCmd = "${env.MAVEN_HOME}/bin/mvn"
                    sh "${mvnCmd} package"
                }
            }
        }


    }


}