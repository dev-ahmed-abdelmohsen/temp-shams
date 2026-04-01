pipeline {
    agent any

    environment {
        IMAGE_NAME = "ahmedshams8/flask-app"
    }

    stages {
        stage('Build Docker Image') {
            steps {
                script {
                    docker.build("${IMAGE_NAME}:latest", ".")
                }
            }
        }

        stage('Push Image') {
            steps {
                script {
                    docker.withRegistry('', '68c08dec-9942-4a47-8acf-2f435afbc7a6') {
                        docker.image("${IMAGE_NAME}:latest").push()
                    }
                }
            }
        }
    }
}
