
pipeline {
    agent any

    environment {
        IMAGE_NAME = "tudor/docker-react"
        DOCKERFILE = "Dockerfile.dev"
    }

    stages {
        stage('Build Docker Image') {
            steps {
                script {
                    sh "docker build -f ${DOCKERFILE} -t ${IMAGE_NAME} ."
                }
            }
        }

        stage('Run Tests') {
            steps {
                script {
                    sh "docker run -e CI=true ${IMAGE_NAME} npm run test"
                }
            }
        }
    }
}
