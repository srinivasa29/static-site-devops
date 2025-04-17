pipeline {
    agent any

    stages {
        stage('Build Docker Image') {
            steps {
                echo '🐳 Building Docker image...'
                script {
                    bat 'docker build -t my-static-site .'
                }
            }
        }

        stage('Run Docker Container') {
            steps {
                echo '🚀 Running Docker container on port 8080...'
                script {
                    bat 'docker rm -f static-site || exit 0'
                    bat 'docker run -d -p 8080:80 --name static-site my-static-site'
                }
            }
        }
    }
}
