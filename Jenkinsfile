pipeline {
    agent any

    stages {

        stage('Clone') {
            steps {
                echo "Repository downloaded successfully"
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t student-app .'
            }
        }

        stage('Stop Old Container') {
            steps {
                sh 'docker stop student-container || true'
                sh 'docker rm student-container || true'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker run -d --name student-container -p 8081:80 student-app'
            }
        }

    }
}
