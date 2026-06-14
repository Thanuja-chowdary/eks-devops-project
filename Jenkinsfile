pipeline {
    agent any

    stages {

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t flask-app:v2 .'
            }
        }

        stage('Load Image To Minikube') {
            steps {
                sh 'minikube image load flask-app:v2'
            }
        }

        stage('Deploy To Kubernetes') {
            steps {
                sh 'kubectl set image deployment/flask-app flask-app=flask-app:v2'
            }
        }

        stage('Verify Deployment') {
            steps {
                sh 'kubectl rollout status deployment/flask-app'
            }
        }
    }
}
