pipeline {
    agent any

    environment {
        DIRECTORY_PATH = './local-environment/'
        TESTING_ENVIRONMENT = 'Staging - SIT 753'
        PRODUCTION_ENVIRONMENT = 'Production - SIT 753' 
    }

    stages {
        stage('Build') {
            steps {
                echo "Fetch the source code from the directory path specified by the environment variable: ${env.DIRECTORY_PATH}"
                echo "Compile the code and generate any necessary artefacts"
            }
        }
        
        stage('Test') {
            steps {
                echo "Unit tests"
                echo "Integration tests"
            }
        }
        
        stage('Code Quality Check') {
            steps {
                echo "Check the quality of the code"
            }
        }
        
        stage('Deploy') {
            steps {
                echo "Deploy the application to a testing environment specified by the environment variable: ${env.TESTING_ENVIRONMENT}"
            }
        }
        
        stage('Approval') {
            steps {
                echo "Simulating manual approval wait time..."
                sleep time: 10, unit: 'SECONDS'
                echo "Approval granted. Proceeding to production deployment."
            }
        }

        stage('Deploy to Staging') {
            steps {
                echo "Successfully deploying the code to the staging environment: ${env.PRODUCTION_ENVIRONMENT}"
            }
        }
        
        stage('Deploy to Production') {
            steps {
                echo "Successfully deploying the code to the production environment: ${env.PRODUCTION_ENVIRONMENT}"
            }
        }
    }
}

