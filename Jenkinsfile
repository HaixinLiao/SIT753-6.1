pipeline {
    agent any
    stages {
        stage('Build') { 
            steps {
                echo "Build the code using Maven to compile and package the code" 
            }
        }
        stage('Unit and Integration Tests') { 
            steps {
                echo "Run unit tests using JUnit to ensure the code functions as expected" 
                echo "Run integration tests using TestNG to ensure the different components of the application work together as expected" 
            }

            post {
                success {
                    mail to: 's223693774@deakin.edu.au'
                }
                failure {
                    mail to: 's223693774@deakin.edu.au'
                }
            }
        }
        stage('Code Analysis') { 
            steps {
                echo "Analyze code quality using SonarQube to ensure it meets industry standards" 
            }
        }
        stage('Security Scan') { 
            steps {
                echo "Perform a security scan using OWASP ZAP to identify any vulnerabilities"  
            }

            post {
                success {
                    mail to: 's223693774@deakin.edu.au'
                }
                failure {
                    mail to: 's223693774@deakin.edu.au'
                }
            }
        }
        stage('Deploy to Staging') { 
            steps {
                echo "Deploy the application to a staging server through AWS EC2" 
            }
        }
        stage('Integration Tests on Staging') {  
            steps {
                echo "Run integration tests using TestNG on the staging environment to ensure the application functions as expected in a production-like environment" 
            }

            post {
                success {
                    mail to: 's223693774@deakin.edu.au'
                }
                failure {
                    mail to: 's223693774@deakin.edu.au'
                }
            }
        }
        stage('Deploy to Production') { 
            steps {
                echo "Deploy the application to a production server through AWS EC2"  
            }
        }
    }
}