pipeline {
    agent any

    environment {
        MAVEN_HOME = tool 'Maven'
    }

    tools {
        maven 'Maven'
    }

    stages {


        stage('Build') {
            steps {
                script {
                     def mvnCmd = tool name: 'Maven', type: 'hudson.tasks.Maven$MavenInstallation'
                     sh "${mvnCmd}/bin/mvn clean install"
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