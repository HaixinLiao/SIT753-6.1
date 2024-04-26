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
                    mail to: 's223693774@deakin.edu.au',
                         subject: 'Unit and Integration Tests succeed',
                         body: 'The Unit and Integration Tests stage succeed. Please see the attached log for details.',
                         attachLog: true
                }
                failure {
                    mail to: 's223693774@deakin.edu.au',
                         subject: 'Unit and Integration Tests Failed',
                         body: 'The Unit and Integration Tests stage failed. Please see the attached log for details.',
                         attachLog: true
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
                    mail to: 's223693774@deakin.edu.au',
                         subject: 'Security Scan succeed',
                         body: 'The Security Scan stage succeed. Please see the attached log for details.',
                         attachLog: true
                }
                failure {
                    mail to: 's223693774@deakin.edu.au',
                         subject: 'Security Scan Failed',
                         body: 'The Security Scan stage failed. Please see the attached log for details.',
                         attachLog: true
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
                    mail to: 's223693774@deakin.edu.au',
                         subject: 'Integration Tests on Staging succeed',
                         body: 'The Integration Tests on Staging stage succeed. Please see the attached log for details.',
                         attachLog: true
                }
                failure {
                    mail to: 's223693774@deakin.edu.au',
                         subject: 'Integration Tests on Staging Failed',
                         body: 'The Integration Tests on Staging stage failed. Please see the attached log for details.',
                         attachLog: true
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