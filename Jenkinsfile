pipeline {
    agent any

    environment {
        VERCEL_TOKEN = credentials('vercel_token') // Make sure this is added in Jenkins credentials
    }

    stages {
        stage('Install') {
            steps {
                // Use 'sh' instead of 'bat' for Linux
                sh 'npm install'
            }
        }

        stage('Test') {
            steps {
                echo 'Skipping tests - no test script found'
            }
        }

        stage('Build') {
            steps {
                sh 'npm run build'
            }
        }

        stage('Deploy') {
            steps {
                // Deploy to Vercel using token from Jenkins credentials
                sh 'npx vercel --prod --yes --token=$VERCEL_TOKEN'
            }
        }
    }
}
