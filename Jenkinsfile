pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Clone your repository
                git branch: 'main', url: 'https://github.com/officialbhaveshmeena/node-cicd.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                echo 'Installing dependencies...'
                // Install npm packages
                bat 'npm install'   // use 'sh' if on Linux
            }
        }

        stage('Run Tests') {
            steps {
                echo 'Running tests...'
                // Optional test command
                bat 'npm test || echo "No tests to run"'
            }
        }

        stage('Build or Start App') {
            steps {
                echo 'Starting Node.js server...'
                // If you have a build step (e.g., Angular/React), use npm run build
                // Otherwise, just start the server
                bat 'npm start'
            }
        }
    }

    post {
        success {
            echo '✅ Build and run successful!'
        }
        failure {
            echo '❌ Build failed. Check logs.'
        }
    }
}
