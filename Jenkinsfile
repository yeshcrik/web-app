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

                script {
                    docker.build("${IMAGE_NAME}:latest")
                }
            }
        }

        stage('Run Docker Container') {
            steps {
                script {
                    // Stop and remove any previous container
                    sh "docker rm -f ${CONTAINER_NAME} || true"
                    
                    // Run the container on port 3000
                    sh "docker run -d -p ${PORT}:${PORT} --name ${CONTAINER_NAME} ${IMAGE_NAME}:latest"
                }
            }
        }
    }
}

