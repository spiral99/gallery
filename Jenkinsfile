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
                sh 'npm run build'
                sh 'npm test'
            }
        }

        stage('Deploy to Render') {
            steps {
                // Start the server using node
                sh 'node server'
            }
        }
    }

    // Automatically trigger the pipeline on every push to the repository
    triggers {
        scm('*/5 * * * *') // Check for changes every 5 minutes
    }
}
