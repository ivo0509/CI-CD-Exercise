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
                // Използваш NodeJS plugin в Jenkins
                tool name: 'NodeJS 18', type: 'nodejs'
            }
        }
        stage('Install dependencies') {
            steps {
                sh 'npm install'
            }
        }
        stage('Start application') {
            steps {
                sh 'nohup npm start &'
                // Изчакай малко, за да се стартира приложението
                sh 'sleep 3'
            }
        }
        stage('Run tests') {
            steps {
                sh 'npm test'
            }
        }
    }
} 