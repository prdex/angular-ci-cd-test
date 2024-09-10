pipeline {
   agent any
    stages {
        stage('Checkout') {
            steps {
                // Checkout code from Git
                git branch: 'main', url: 'https://github.com/prdex/angular-ci-cd-test.git', credentialsId: 'd854b73a57974779886700e10b64253a'
            }
        }
        stage('Install Dependencies') {
            steps {
                // Install Node.js dependencies
                sh 'npm install'
            }
        }
        stage('Build Angular App') {
            steps {
                // Build the Angular application
                sh 'ng build --prod'
            }
        }
        stage('Test') {
            steps {
                // Run tests (optional)
                sh 'ng test --watch=false'
            }
        }
        stage('Archive Artifacts') {
            steps {
                // Archive build artifacts
                archiveArtifacts artifacts: 'dist/**', allowEmptyArchive: true
            }
        }
    }
}
