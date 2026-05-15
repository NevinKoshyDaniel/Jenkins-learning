pipeline {
    agent any

    environment {
        DIRECTORY_PATH = './local-environment/'
        STAGING_ENVIRONMENT = 'Staging - SIT 753'
        PRODUCTION_ENVIRONMENT = 'Production - SIT 753' 
    }

    stages {
        stage('Build') {
            steps {
                echo "Fetch the source code from the directory path specified by the environment variable: ${env.DIRECTORY_PATH}"
                echo "Running the build using NPM and node"
                echo "Compiled the code and generate any necessary artefacts"
            }
        }
        
        stage('Unit and Integration Test') {
            steps {
                echo "Unit tests"
                echo "Integration tests"
            }
        }
        
        stage('Code Quality Check - Sonarqube') {
            steps {
                echo "Checking the quality of the code"
                echo "Running Sonarqube"
            }
        }
        
        stage('Security Scan')
        {
            steps {
                echo "Synk is initialized"
                echo "Security scans are running"
            }
        }

        stage('Deploy to staging') {
            steps {
                echo "Deploying on our AWS staging area"
                echo "Successfully deploying the code to the staging environment: ${env.STAGING_ENVIRONMENT}"
             }
        }
        
        stage('Integrity checks ') {
            steps {
                echo "Simulating integrity checks in the staging area"
                sleep time: 10, unit: 'SECONDS'
                echo "Approval granted. Proceeding to production deployment."
            }
        }
 
        stage('Deploy to Production') {
            steps {
                echo "Successfully deploying the code to the production environment: ${env.PRODUCTION_ENVIRONMENT}"
            }
        }
    }
}

