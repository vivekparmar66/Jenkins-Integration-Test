pipeline {
    agent any
    stages {
        stage('vivek - Build Docker Image') {
            steps {
                sh 'docker build -t vivekparmar12/jenkins-pipeline-test:latest .'
            }
        }
        stage('vivek - Login to DockerHub') {
            steps {
                withCredentials([usernamePassword(credentialsId: 'dockerhub-credentials', usernameVariable: 'DOCKER_USERNAME', passwordVariable: 'DOCKER_PASSWORD')]) {
                    sh 'echo $DOCKER_PASSWORD | docker login -u $DOCKER_USERNAME --password-stdin'
                }
            }
        }
        stage('vivek - Push image to DockerHub') {
            steps {
                sh 'docker push vivekparmar12/jenkins-pipeline-test:latest'
            }
        }
    }
}