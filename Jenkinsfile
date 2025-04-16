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
                // Run the Docker container in detached mode
                sh 'docker run -d -p 3000:3000 --name web-app web-app:latest'
            }
        }
    }
}

