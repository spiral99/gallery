pipeline {
    agent any

    stages {
        stage('Clone repository') {
            steps {
                // Checkout the repository
                git 'https://github.com/spiral99/gallery.git'
            }
        }

        stage('Install dependencies') {
            steps {
                // Ensure required software is available
                sh 'npm install'
            }
        }

        stage('Build and test') {
            steps {
                // Build and test your application (replace with your own commands)
                sh 'npm run'
                sh 'npm test'
            }
        }

        stage('Deploy to Render') {
            steps {
                // Start the server using node
                sh 'BUILD_ID=dontKillMe npm start &'
            }
        }
    }
}
