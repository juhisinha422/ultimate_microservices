pipeline {
    agent any

    stages {

        stage('Build Docker Image') {
            steps {
                dir('src') {
                    script {
                        withDockerRegistry(credentialsId: 'docker-cred', toolName: 'docker') {
                            sh "docker build -t juhisinha/cartservice:latest ."
                        }
                    }
                }
            }
        }

        stage('Push Docker Image') {
            steps {
                script {
                    withDockerRegistry(credentialsId: 'docker-cred', toolName: 'docker') {
                        sh "docker push juhisinha/cartservice:latest"
                    }
                }
            }
        }
    }
}
