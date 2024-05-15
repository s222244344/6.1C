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
                always {
                    emailext(
                        to: "tamir.uni1@gmail.com",
                        subject: "Unit and Integration testing: Success",
                        body: "<p>Stage 'Unit and Integration Tests' completed with status ${currentBuild.result}</p><p>Check console output at ${env.BUILD_URL} to view the result.</p>",
                        attachLog: true
                    )
                }
            }
        }
        stage('Code Analysis') {
            steps {
                echo "Running SonarQube scanner..."
                echo "Analyzing code..."
            }
        }
        stage('Security Scan') {
            steps {
                echo "Running OWASP Dependency-Check to perform security scan..."
            }
            post {
                always {
                    emailext(
                        to: "tamir.uni1@gmail.com",
                        subject: "Security scan successful",
                        body: "<p>Stage 'Security Scan' completed with status ${currentBuild.result}</p><p>Check console output at ${env.BUILD_URL} to view the result.</p>",
                        attachLog: true
                    )
                }
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
