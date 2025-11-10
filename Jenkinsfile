pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Pull code from Git
                git branch: 'main', url: 'https://github.com/yourusername/your-repo.git'
            }
        }

        stage('Lint') {
            steps {
                echo "Running lint..."
                // Example lint command
                sh 'npm install'         // If using Node.js
                sh 'npm run lint'        // Replace with your lint command
                // For Python: sh 'flake8 .'
                // For Java/Kotlin: sh './gradlew ktlintCheck'
            }
        }
    }

    post {
        success {
            echo 'Checkout and lint completed successfully!'
        }
        failure {
            echo 'Pipeline failed during checkout or lint.'
        }
    }
}