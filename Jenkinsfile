pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building...'
                sh 'mvn clean package' // Adjust according to your build tool
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                echo 'Running Unit and Integration Tests...'
                sh 'mvn test' // Adjust according to your test framework
            }
        }
        stage('Code Analysis') {
            steps {
                echo 'Performing Code Analysis...'
                sh 'sonar-scanner' // Assuming you have SonarQube setup
            }
        }
        stage('Security Scan') {
            steps {
                echo 'Running Security Scan...'
                sh 'snyk test' // Assuming you have Snyk CLI installed
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo 'Deploying to Staging...'
                sh 'scp target/yourapp.war user@staging-server:/path/to/deploy' // Example
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                echo 'Running Integration Tests on Staging...'
                // Add your testing steps here
            }
        }
        stage('Deploy to Production') {
            steps {
                echo 'Deploying to Production...'
                sh 'scp target/yourapp.war user@production-server:/path/to/deploy' // Example
            }
        }
    }

    post {
        always {
            emailext (
                to: 'developer@example.com',
                subject: "Build ${currentBuild.fullDisplayName}",
                body: "Build ${currentBuild.fullDisplayName} finished with status ${currentBuild.result}",
                attachLog: true
            )
        }
    }
}
