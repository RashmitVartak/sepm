pipeline {
    agent any
    tools { 
        nodejs "LatestNode" // Ensure Node.js is installed
    }
    stages {
        stage('Install npm packages') {
            steps {
                bat 'cd frontend && npm install' // Navigate to frontend directory and install dependencies
            }
        }
        stage('Build frontend') {
            steps {
                bat 'cd frontend && npm run build' // Build the frontend
            }
        }
        stage('Install backend npm packages') {
            steps {
                bat 'cd backend && npm install' // Navigate to backend directory and install dependencies
            }
        }
        stage('Build backend') {
            steps {
                bat 'cd backend && npm run build' // If necessary, run any build commands for the backend
            }
        }
        stage('Deploy to IIS') {
            steps {
                bat 'Xcopy frontend/build C:\\inetpub\\wwwroot\\Devops /E /H /C /I /Y' // Copy frontend build to IIS directory
                bat 'Xcopy backend C:\\path\\to\\backend\\directory /E /H /C /I /Y' // Copy backend files to appropriate directory
                // Make sure to replace 'C:\\path\\to\\backend\\directory' with the correct path for your backend
            }
        }
    }
}
