pipeline {
    agent any

    stages {
        stage('Clone') {
            steps {
                git branch: 'main', url: 'https://github.com/Laxmi7676/jenkins-cicd.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t jenkins-cicd:v1 .'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker rm -f jenkins-container || true'
                sh 'docker run -d --name jenkins-container jenkins-cicd:v1'
            }
        }
    }
}

