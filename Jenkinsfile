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
                bat 'npm ci'
            }
        }
        stage('Start application') {
            steps {
                bat 'start /B npm start'
                // Изчакай малко, за да се стартира приложението
                bat 'timeout /T 3'
            }
        }
        stage('Run tests') {
            steps {
                bat 'npm test'
            }
        }
    }
}