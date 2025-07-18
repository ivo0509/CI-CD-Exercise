pipeline {
    agent any
    stages {
        stage('Checkout code') {
            steps {
                checkout scm
            }
        }
        stage('Set up Node.js') {
            steps {
                tool name: 'NodeJS 18', type: 'nodejs'
            }
        }
        stage('Install dependencies') {
            steps {
                echo 'npm ci'
            }
        }
        stage('Start application') {
            steps {
                bat 'start "" cmd /c "npm start"'
            

            }
        }
        stage('Run tests') {
            steps {
                echo 'npm test'
            }
        }
    }
}