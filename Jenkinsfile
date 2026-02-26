pipeline {
    agent any

    stages {

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t supermarket:v2 .'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker stop supermarket || true'
                sh 'docker rm supermarket || true'
                sh 'docker run -d -p 8090:80 --name supermarket supermarket:v2'
            }
        }

    }
}
