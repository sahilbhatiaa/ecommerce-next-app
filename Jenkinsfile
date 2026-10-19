
pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'npm ci'
            }
        }

        stage('Build Next.js') {
            steps {
                sh 'npm run build'
            }
        }
    }

    post {
        success {
            echo 'Next.js build completed successfully!'
        }

        failure {
            echo 'Build failed. Check the Console Output.'
        }
    }
}
