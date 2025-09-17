pipeline {
    agent any

    tools {
        nodejs "NodeJS_22"
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'master',
                url: 'https://github.com/<your-username>/hello-devops.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'npm install'
            }
        }

        stage('Test') {
            steps {
                sh 'npm test'
            }
        }

        stage('Build') {
            steps {
                echo 'Building the project...'
            }
        }

        stage('Run') {
            steps {
                sh 'npm start & sleep 5 && curl -s http://localhost:3000'
            }
        } 
    }

    post {
        always {
            echo 'Pipeline finished.'
        }
    }
}