pipeline {
    agent any

    stages {
        stage('Clone') {
            steps {
                // Pull the code from GitHub
                git 'git@github.com:yeshcrik/web-app.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    // Build the Docker image
                    docker.build("web-app:latest")
                }
            }
        }

        stage('Run Docker Container') {
            steps {
                script {
                    // Run the Docker container
                    sh 'docker run -d -p 3000:3000 --name web-app web-app:latest'
                }
            }
        }
    }
}
