// pipeline {
//     agent any
//      tools {
//         nodejs 'NodeJS 21.1'
//     }
//     stages {
//         stage('Checkout') {
//             steps {
//                 cleanWs()  // Clean the workspace before checkout
//                 echo "Checking out..."
//                 checkout scm  // Checkout the code from the repository
//             }
//         }
//         stage('Install Dependencies') {
//             steps {
//                 script {
//                     echo "Installing dependencies..."
//                     sh 'npm install'  // Run npm install to install dependencies
//                 }
//             }
//         }
//          stage('Build') {
//             steps {
//                 // Build Next.js project
//                 nodejs(nodeJSInstallationName: 'NodeJS 21.1') {
//                     sh 'npm run build'
//                 }
//             }
//         }
//     }
// }



// pipeline {
//     agent any
//     tools {
//         nodejs 'NodeJS 21.1'
//     }
//     stages {
//         stage('Checkout') {
//             steps {
//                 cleanWs()  // Clean the workspace before checkout
//                 echo "Checking out..."
//                 checkout scm  // Checkout the code from the repository
//             }
//         }
//         stage('Install Dependencies') {
//             steps {
//                 script {
//                     echo "Installing dependencies..."
//                     sh 'npm install'  // Run npm install to install dependencies
//                 }
//             }
//         }
//         stage('Build') {
//             steps {
//                 // Set the NODE_OPTIONS to use the legacy OpenSSL provider to avoid the error
//                 script {
//                     echo "Setting NODE_OPTIONS for OpenSSL legacy provider..."
//                     sh 'export NODE_OPTIONS=--openssl-legacy-provider'
//                 }
//                 // Build React project
//                 nodejs(nodeJSInstallationName: 'NodeJS 21.1') {
//                     sh 'npm run build'
//                 }
//             }
//         }
//     }
// }

pipeline {
    agent any
    tools {
        nodejs 'nodejs-16.12'  // Use the correct nodejs version installed in Jenkins
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
                    sh 'npm install'  // Install dependencies using npm
                }
            }
        }
        stage('Build') {
            steps {
                // Ensure build is executed using Node 16.12
                nodejs(nodeJSInstallationName: 'nodejs-16.12') {
                    echo "Building the React project..."
                    sh 'npm run build'  // Build the React project
                }
            }
        }
    }
}


