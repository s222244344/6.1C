pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
             echo "using Maven to automatically compile and package code...."
            }
        }
        stage('Unit and Integration testing') {
            steps {
             echo "Running unit testing using JUnit...."
                echo "Running integration tests using Selenium...."
            }
        }
        stage('Code Analysis') {
            steps {
                echo "RunSonarQube scanner...."
                echo"analysing code...."
                
            }
        }
        stage('Security Scan') {
            steps {
                echo "Running OWASP Dependency-check to perfrom security scan......"
            }
        }
        stage('Deploy to staging ') {
            steps {
                echo "Use AWS CodeDeploy to deploy to staging...."
                echo "Deploying the application to staging server: SLB TYA...."
                
            }
        }
        stage('Integration Tests on saging') {
            steps {
                echo "Executing integration tests using Selenium...."
                echo "mvn test -Dtest=IntegrationTest...."
                
            }
        }
        stage('Deploy to production')
        steps{
            echo "Using AWS COdeDeploy to deploy the application to production...."
            echo "aws deploy create-deployment...."
              echo "application-name <SIT223_APPLICATION..>"
    } 
}
