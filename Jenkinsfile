pipeline {
    agent any
   
    }
    stages {
        stage('Checkout') {
            steps {
                // Checkout the source code from the Git repository
                git 'https://github.com/rat9615/simple-nodejs-app'
            }
        }
        stage('Install Dependencies') {
            steps {
                // Install Node.js dependencies
                sh 'npm install'
            }
        }
        stage('Run Tests') {
            steps {
                // Run tests to ensure code quality
                sh 'npm test'
            }
        }
        stage('Build') {
            steps {
                // Build the application
                sh 'npm run build'
            }
        }
        stage('Deploy') {
            steps {
                // Deploy the application
                // This could involve building and deploying a Docker container or deploying to a cloud service
                // Example using Docker
                script {
                    sh 'docker build -t my-app-image .'
                    sh 'docker run -d -p 80:80 my-app-image'
                }
            }
        }
    }
    post {
        success {
            echo 'Build and deployment successful!'
        }
        failure {
            echo 'Build or deployment failed.'
            // Additional actions on failure, such as notifications or cleanup
        }
    }
}
