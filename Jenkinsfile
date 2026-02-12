pipeline {
    agent any

    environment {
        DOCKER_IMAGE = "renupatil08/website"
    }

    stages {

        stage('Clone') {
            steps {
                git 'pipeline {
    agent any

    environment {
        DOCKER_IMAGE = "yourdockerhubusername/website"
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

        stage('Deploy to Kubernetes') {
            steps {
                sh '''
                kubectl set image deployment/website website=${DOCKER_IMAGE}:${BUILD_NUMBER} || \
                kubectl create deployment website --image=${DOCKER_IMAGE}:${BUILD_NUMBER}
                '''
            }
        }
    }
}
'
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

        stage('Deploy to Kubernetes') {
            steps {
                sh '''
                kubectl set image deployment/website website=${DOCKER_IMAGE}:${BUILD_NUMBER} || \
                kubectl create deployment website --image=${DOCKER_IMAGE}:${BUILD_NUMBER}
                '''
            }
        }
    }

