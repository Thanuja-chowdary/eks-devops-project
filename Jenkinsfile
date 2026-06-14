pipeline {
    agent any

    stages {

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t flask-app:v2 .'
            }
        }

        stage('Verify Image') {
            steps {
                sh 'docker images | grep flask-app'
            }
        }
    }
}

