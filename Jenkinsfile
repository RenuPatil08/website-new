pipeline {
    agent any

    environment {
        DOCKER_IMAGE = "renupatil08/website-new"
    }

    stages {

        stage('Clone') {
            steps {
                git 'https://github.com/RenuPatil08/website-new.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    docker.build("${DOCKER_IMAGE}:${BUILD_NUMBER}")
                }
            }
        }

        stage('Push Image') {
            steps {
                script {
                    docker.withRegistry('', 'dockerhub-creds') {
                        docker.image("${DOCKER_IMAGE}:${BUILD_NUMBER}").push()
                    }
                }
            }
        }
    }
}

