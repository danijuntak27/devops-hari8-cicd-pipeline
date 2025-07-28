pipeline {
    agent any

    stages {
        stage('Clone Repo'){
            steps {
                git 'https://github.com/danijuntak27/devops-hari8-cicd-pipeline.git'
            }
        }
        stage('Build Docker Image'){
            steps {
                script{
                    sh'docker build -t flask-cicd .'
                }
            }
        }
        stage ('Run Container'){
            steps {
                script{
                    sh 'docker rm -f flask-cicd-container || true '
                    sh 'docker run -d --name flask-cicd-container -p 5000:5000 flask-cicd'
                }
            }
        }
    }
}
