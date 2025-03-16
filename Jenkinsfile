pipeline {
    agent any

    environment {
        DOCKER_IMAGE = 'my-node-app'
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main',
                url: 'https://github.com/saitejatamiri/node-hello-world.git'
                sh "ls -a"
                sh "pwd"
            }
        }
    stage('Build') {
            steps {
                script {
                   sh "docker build -t saitejatamiri/123:tag123 ."
                   sh "docker images"
                   sh "docker image prune"
                   sh "docker images"
                   withDockerRegistry(credentialsId: '80e1f97d-af70-4380-b374-823f78b7872e') {
                       sh "docker push saitejatamiri/123:tag123"
                    }
                }
            }
        }

    }
    
}
