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
            // Sending email notification with build status
            script {
                emailext(
                    to: 'anjanam9339@gmail.com',
                    subject: "Pipeline Status: ${currentBuild.currentResult}",
                    body: """
                    The pipeline ${env.JOB_NAME} build #${env.BUILD_NUMBER} has completed with status: ${currentBuild.currentResult}.
                    
                    - Job URL: ${env.BUILD_URL}
                    - Build Log: ${env.BUILD_URL}console
                    """,
                    attachLog: true // Optionally, attach the console log if needed
                )
            }
        }
    }
}
