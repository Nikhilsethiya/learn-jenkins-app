pipeline {
    agent any

    stages {
        stage('Clean Workspace') {
            steps {
                cleanWs() // Cleans the workspace
            }
        }
        stage('Build') {
            agent {
                docker {
                    image 'node:18-alpine'
                    reuseNode true
                }
            }
            steps {
                sh '''
                echo "Node.js Version:"
                node --version

                echo "NPM Version:"
                npm --version

                echo "Installing dependencies..."
                npm install

                echo "Starting the application..."
                npm start
                '''
            }
        }
    }
}
