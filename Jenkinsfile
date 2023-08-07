pipeline {
    agent any
    environment {
            NAME = 'John'
        }
    stages {
        stage('Build') {
            steps {
                 echo "Building"
                 echo "My Name is  $NAME"
            }
        }
        stage('Test') {
            steps {
                echo "Test"
            }
        }
        stage('Deploy') {
            steps {
                echo "Deploy"
            }
        }
    }
}