pipeline {
    agent any

    stages {
        stage('Clone Code') {
            steps {
                echo 'Cloning repository...'
                git 'https://github.com/vishalglobe/html-docker.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                echo 'Building Docker image...'
                sh 'docker build -t myapp .'
            }
        }

        stage('Run Docker Container') {
            steps {
                echo 'Running Docker container...'
                sh '''
                docker rm -f html-container || true
                docker run -d -p 80:80 --name html-container myapp
                '''
            }
        }
    }
}

