pipeline {
    agent any

    environment {
        DOCKER_IMAGE = 'esha27/my-app'
        AWS_REGION = 'us-east-1'
        CLUSTER_NAME = 'ecommerce-cluster'
    }

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    docker.build("${DOCKER_IMAGE}")
                }
            }
        }

        stage('Push to Docker Hub') {
            steps {
                script {
