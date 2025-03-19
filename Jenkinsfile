pipeline {
    agent any

    stages {
        stage('Checkout Code') {
            steps {
                git 'https://github.com/Gopi4891/CI-CD-Project.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    sh 'docker build -t gopi-html-app .'
                }
            }
        }

        stage('Run Docker Container') {
            steps {
                script {
                    sh 'docker stop gopi-container || true'
                    sh 'docker rm gopi-container || true'
                    sh 'docker run -d -p 8080:80 --name gopi-container gopi-html-app'
                }
            }
        }
    }
}
