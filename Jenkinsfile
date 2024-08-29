pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building...'
                echo 'Tool: Maven could be used for build automation.'
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                echo 'Running Unit and Integration Tests...'
                echo 'Tools: JUnit or TestNG could be used for unit and integration testing.'
            }
        }
        stage('Code Analysis') {
            steps {
                echo 'Performing Code Analysis...'
                echo 'Tool: SonarQube could be used for static code analysis.'
            }
        }
        stage('Security Scan') {
            steps {
                echo 'Running Security Scan...'
                echo 'Tools: OWASP ZAP or Snyk could be used for security scanning.'
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo 'Deploying to Staging...'
                echo 'Tool: SCP or a deployment service like AWS CodeDeploy could be used for staging deployment.'
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                echo 'Running Integration Tests on Staging...'
                echo 'Tool: Selenium or Postman could be used for integration testing in staging.'
            }
        }
        stage('Deploy to Production') {
            steps {
                echo 'Deploying to Production...'
                echo 'Tool: SCP or a deployment service like AWS CodeDeploy could be used for production deployment.'
            }
        }
    }

    post {
        always {
            emailext (
                to: 'maxiecletus@gmail.com',
                subject: "Build ${currentBuild.fullDisplayName}",
                body: "Build ${currentBuild.fullDisplayName} finished with status ${currentBuild.result}",
                attachLog: true
            )
        }
    }
}
