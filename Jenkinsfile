
pipeline {
    agent any

    environment {
        IMAGE_NAME = 'villa-website'
        PORT = '8000'
    }

    stages {
        stage('Clean Workspace') {
            steps {
                deleteDir()
            }
        }

        stage('Clone Repository') {
            steps {
               
                    git branch: 'Main', url: 'https://github.com/devilraj98/Villa-website-hosting.git'
              
            }
        }

        stage('Build Docker Image') {
            steps {
                sh '''
                
                    docker build -t ${IMAGE_NAME} .
                '''
            }
        }
        stage('Push to Docker Hub') {
            steps {
                withCredentials([usernamePassword(credentialsId: 'dockerhub-credentials', usernameVariable: 'DOCKER_USERNAME', passwordVariable: 'DOCKER_PASSWORD')]) {
                    sh '''
                        echo $DOCKER_PASSWORD | docker login -u $DOCKER_USERNAME --password-stdin
                        docker tag ${IMAGE_NAME} $DOCKER_USERNAME/${IMAGE_NAME}:latest
                        docker push $DOCKER_USERNAME/${IMAGE_NAME}:latest
                    '''
                }
            }
        }
        stage('Deploy') {
            steps {
                sh '''
                    docker compose down --remove-orphans || true
                    docker compose up -d
                '''
            }
        }
    }

    post {
        success {
            echo "✅ Site deployed at http://<vinod-IP>:${PORT}"
        }
        failure {
            echo "❌ Deployment failed."
        }
    }


}

