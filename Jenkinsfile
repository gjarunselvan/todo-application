pipeline {
    agent any

    environment {
        DOCKER_IMAGE = "gjarunselvan/todo-application:latest"
    }

    stages {

        stage('Checkout') {
            steps {
                git 'https://github.com/gjarunselvan/todo-application.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean package -DskipTests'
            }
        }

        stage('Docker Build') {
            steps {
                sh 'docker build -t $DOCKER_IMAGE .'
            }
        }

        stage('Docker Push') {
            steps {
                sh 'docker push $DOCKER_IMAGE'
            }
        }
    }
}
