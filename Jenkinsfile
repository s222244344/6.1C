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
                     mail to: "tamir.uni1@gmail.com",
                    subject: "Unit and Integration testing: Success",
                     body: "Unit and Integration testing stage successful",
                   
                  
                }
                failure {
                      mail to: "tamir.uni1@gmail.com"
                    body: "Unit and Integration testing stage unsuccessful",
                    subject: "Unit and Integration testing: Unsuccessful",
                 
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
                success {
                           mail to: "tamir.uni1@gmail.com"
                     body: "Security Scan passed successfully",
                    subject: "Security scan successful",
             
                }
                failure {
                          mail to: "tamir.uni1@gmail.com"
                     body: "Security scan unsuccessful",
                    subject: "Security scan unsuccessful",
             
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
