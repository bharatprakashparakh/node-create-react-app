pipeline {
    agent any
     tools {
        nodejs 'NodeJS 21.1'
    }
    stages {
        stage('Checkout') {
            steps {
                cleanWs()  // Clean the workspace before checkout
                echo "Checking out..."
                checkout scm  // Checkout the code from the repository
            }
        }
        stage('Install Dependencies') {
            steps {
                script {
                    echo "Installing dependencies..."
                    sh 'npm install'  // Run npm install to install dependencies
                }
            }
        }
         stage('Build') {
            steps {
                // Build Next.js project
                nodejs(nodeJSInstallationName: 'NodeJS 21.1') {
                    sh 'npm run build'
                }
            }
        }
    }
}
