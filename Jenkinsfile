 
pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building the project...'
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                echo 'Running unit and integration tests...'                
            }
        }
        stage('Code Analysis') {
            steps {
                echo 'Performing code analysis...'
            }
        }
        stage('Security Scan') {
            steps {
                echo 'Performing security scan...'
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo 'Deploying to staging environment...'
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                echo 'Running integration tests on staging...'
            }
        }
        stage('Deploy to Production') {
            steps {
                echo 'Deploying to production environment...'
            }
        }
    }

    post {
        always {
            echo 'Sending notification email...'
            // Sending email notification with stage status and logs as attachment
            script {
                emailext (
                    to: 'anjanam9339@gmail.com',
                    subject: "Pipeline Status: ${currentBuild.currentResult}",
                    body: "The pipeline has finished with status: ${currentBuild.currentResult}. Please find the attached logs.",
                    attachmentsPattern: '**/*.log'
                )
            }
        }
    }
}
