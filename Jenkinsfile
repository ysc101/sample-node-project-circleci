pipeline {
    agent any

    environment {
        NODE_ENV = 'production' // Set the Node.js environment
    }

    stages {
        stage('Clone Repository') {
            steps {
                script {
                    // Clone the repository
                    git branch: 'master', url: 'https://github.com/ysc101/sample-node-project-circleci.git'
                }
            }
        }

        stages {
        stage('Install Dependencies') {
            steps {
                script {
                    echo 'Installing dependencies...'
                    bat 'npm install'  // Use bat for Windows shell commands
                }
            }
        }
        stage('Start Application') {
            steps {
                script {
                    echo 'Starting application...'
                    bat 'start /B npm start'  // Start in background for Windows
                }
            }
        }
    }

    post {
        success {
            echo 'Pipeline executed successfully!'
        }
        failure {
            echo 'Pipeline execution failed!'
        }
    }
}
