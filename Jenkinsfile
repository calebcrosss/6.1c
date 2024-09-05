pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building with Maven!'
            }
        }
        
        stage('Unit and Integration Tests') {
            steps {
                echo 'Running Unit tests with Junit and Integration Selenium for integration testing'
            }
            post {
                success {
                    emailext (
                        subject: "Unit and integration tests success",
                        body: "The JUnit and Selenium tests have beeen completed successfully.",
                        to: 'caleb.cc.cross@gmail.com',
                        attachLog: true
                    )
                }
                
                failure {
                    emailext (
                        subject: "Unit and integration tests failed",
                        body: "The JUnit and/or Selenium tests have failed.",
                        to: 'caleb.cc.cross@gmail.com',
                        attachLog: true
                    )
                }
            }
        }
        
        stage('Code Analysis') {
            steps {
                echo 'Performing Code Analysis with SonarQube'
            }
        }
        
        stage('Security Scan') {
            steps {
                echo 'Performing Security Scan with OWASP ZAP'
            }
            post {
                success {
                    emailext (
                        subject: "Security scan success",
                        body: "The OWASP ZAP security scans have beeen completed successfully.",
                        to: 'caleb.cc.cross@gmail.com',
                        attachLog: true
                    )
                }
                
                failure {
                    emailext (
                        subject: "Security scan failed",
                        body: "The OWASP ZAP security scans have failed.",
                        to: 'caleb.cc.cross@gmail.com',
                        attachLog: true
                    )
                }
            }
        }
        
        stage('Deploy to Staging') {
            steps {
                echo 'Deploying to Staging using an AWS EC2 instance'
            }
        }
        
        stage('Integration Tests on Staging') {
            steps {
                echo 'Running Integration Tests on Staging using Selenium'
            }
            post {
                success {
                    emailext (
                        subject: "Integration tests success!!",
                        body: "The selenium integration tests on staging have been completed successfully.",
                        to: 'caleb.cc.cross@gmail.com',
                        attachLog: true
                    )
                }
                
                failure {
                    emailext (
                        subject: "Integration tests failed",
                        body: "The selenium integration tests on staging have failed.",
                        to: 'caleb.cc.cross@gmail.com',
                        attachLog: true
                    )
                }
            }
        }
        
        stage('Deploy to Production') {
            steps {
                echo 'Deploying to Production with an AWS EC2 instance'
            }
        }
    }
}
