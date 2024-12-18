pipeline {
    agent any  // Use any available agent

    environment {
        // Define any environment variables here
        GIT_REPO = 'https://github.com/Mihunraj/my_jenkins_example.git'
        BRANCH = 'main'
    }

    stages {
        stage('Checkout') {
            steps {
                // Checkout the code from the Git repository
                git branch: "${BRANCH}", url: "${GIT_REPO}"
            }
        }

        stage('Build') {
            steps {
                // Build the application (e.g., using Maven, Gradle, etc.)
                sh 'mvn clean package'  // Example for a Maven project
            }
        }

        stage('Test') {
            steps {
                // Run tests
                sh 'mvn test'  // Example for a Maven project
            }
        }

        stage('Deploy') {
            steps {
                // Deploy the application (this could be to a server, cloud, etc.)
                sh 'echo "Deploying application..."'  // Replace with actual deployment command
            }
        }
    }

    post {
        success {
            // Actions to take on success
            echo 'Pipeline completed successfully!'
        }
        failure {
            // Actions to take on failure
            echo 'Pipeline failed!'
        }
        always {
            // Actions to take regardless of success or failure
            cleanWs()  // Clean up the workspace
        }
    }
}
