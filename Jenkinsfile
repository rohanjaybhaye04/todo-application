pipeline {
    agent any

    environment {
        DOCKERHUB_CREDENTIALS = 'docker-hub-credentials'
        DOCKER_IMAGE = 'todo-application-image:latest'
        DOCKER_REPO = 'rohanjaybhaye04/todo-application:latest'
    }

    stages {
        stage('Clone Repository') {
            steps {
                git url: 'https://github.com/rohanjaybhaye04/todo-application.git', branch: 'master'
            }
        }
        stage('Build with Maven') {
            steps {
                sh 'mvn clean package -DskipTests'
            }
        }
        stage('Build Docker Image') {
            steps {
                script {
                    sh "docker build -t ${DOCKER_IMAGE} ."
                }
            }
        }
        stage('Push Docker Image to Docker Hub') {
            steps {
                withCredentials([usernamePassword(credentialsId: "${DOCKERHUB_CREDENTIALS}", usernameVariable: 'DOCKERHUB_USER', passwordVariable: 'DOCKERHUB_PASS')]) {
                    sh "echo ${DOCKERHUB_PASS} | docker login -u ${DOCKERHUB_USER} --password-stdin"
                    sh "docker tag ${DOCKER_IMAGE} ${DOCKER_REPO}"
                    sh "docker push ${DOCKER_REPO}"
                }
            }
        }
        stage('Deploy with Docker Compose') {
            steps {
                sh 'docker compose up -d'
            }
        }
        stage('Verify Services') {
            steps {
                sh 'docker compose ps'
            }
        }
        stage('Clean Workspace') {
            steps {
                sh 'rm -rf *'
            }
        }
    }
    post {
        success {
            echo 'Build and deployment successful!'
        }
        failure {
            echo 'Build or deployment failed.'
        }
    }
}
