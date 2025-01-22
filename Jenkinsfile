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
                    git branch: 'main', url: 'https://github.com/ysc101/sample-node-project-circleci.git'
                }
            }
        }

        stage('Install Dependencies') {
            steps {
                script {
                    // Navigate to the project directory and install dependencies
                    sh '''
                    cd sample-node-project
                    npm install
                    '''
                }
            }
        }

        stage('Start Application') {
            steps {
                script {
                    // Start the Node.js application
                    sh '''
                    cd sample-node-project
                    npm start
                    '''
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
