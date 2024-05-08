pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo "Using Maven to automatically compile and package code..."
            }
        }
        stage('Unit and Integration testing') {
            steps {
                echo "Running unit testing using JUnit..."
                echo "Running integration tests using Selenium..."
            }
            post {
                success {
                    mail body: unit and Integration testing stage successull"
                    subject: "Unit and Integration testing: Success"
                    to: "s222244344@deakin.edu.au",
                        attachLog: true
        }
        stage('Code Analysis') {
            steps {
                echo "Running SonarQube scanner..."
                echo "Analyzing code..."
            }
        }
                failure {
                    mail body: "Unit and Integration testing stage unsuccessful"
                    subject: "Unit and Integration testing: unsuccessful"
                    to: "s222244344@deakin.edu.au"
                    attachLog: true
        stage('Security Scan') {
            steps {
                echo "Running OWASP Dependency-Check to perform security scan..."
            }
        }
        stage('Deploy to staging') {
            steps {
                echo "Using AWS CodeDeploy to deploy to staging..."
                echo "Deploying the application to staging server: SLB TYA..."
            }
        }
        stage('Integration Tests on staging') {
            steps {
                echo "Executing integration tests using Selenium..."
                echo "mvn test -Dtest=IntegrationTest..."
            }
        }
        stage('Deploy to production') {
            steps {
                echo "Using AWS CodeDeploy to deploy the application to production..."
                echo "aws deploy create-deployment..."
                echo "application-name <SIT223_APPLICATION>..."
            }
        }
    }
}
