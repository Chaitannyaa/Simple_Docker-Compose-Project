pipeline {
    agent {
        label 'prod'
    }
    environment {
        DOCKER_IMAGE_TAG = "${BUILD_NUMBER}"
    }
    stages {
        stage ("code"){
            steps {
                git url: 'https://github.com/Chaitannyaa/Simple_Docker-Compose-Project.git', branch: 'prod'
            }
        }
        stage ("Build"){
            steps {
                sh 'docker build -t chaitannyaa/flask-vote-app:v-${DOCKER_IMAGE_TAG} .'
            }
        }
        stage ("Push image to docker registry"){
            steps {
                echo 'Logging into docker and pushing an image on dockerhub'
                withCredentials([usernamePassword(credentialsId: 'DockerHub', passwordVariable: 'password', usernameVariable: 'user')]) {
                    sh "docker login -u ${env.user} -p ${env.password}"
                    sh "docker push chaitannyaa/flask-vote-app:v-${DOCKER_IMAGE_TAG}"
                }
            }
        }
        stage ("Deploy"){
            steps {
                sh 'docker-compose down && docker-compose up -d'
                sh 'docker system prune'
            }
        }
    }
}
