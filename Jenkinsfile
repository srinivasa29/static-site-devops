pipeline {
    agent any

    stages {
        stage('Build Docker Image') {
            steps {
                sh 'docker build -t my-static-site .'
            }
        }

        stage('Run Docker Container') {
            steps {
                sh 'docker rm -f static-site || true'
                sh 'docker run -d -p 8080:80 --name static-site my-static-site'
            }
        }
    }
}
