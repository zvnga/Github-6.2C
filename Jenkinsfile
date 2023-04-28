pipeline{
    agent any
    environment {
        DIRECTORY_PATH= "/Users/zungasiakalima/.jenkins/workspace/6.2 C O Github"
        TESTING_ENVIRONMENT= "6.2 C O Github"
        PRODUCTION_ENVIRONMENT= "Zunga"
    }
    stages{
        stage('Build')
            steps{
                echo "Build the code using Maven in order to compile and package it"
                echo "$DIRECTORY_PATH"
        
        }
        stage('Unit and Integration Tests'){
            steps{
                echo "Ensure code functions run as expected and application components work together "
                echo "$TESTING_ENVIRONMENT"
            } 
        
        }
        stage('Code Analysis'){
            steps{
                echo "Use the code analysis tool 'SonarQube' to analyse the code and ensure it meets industry standards"
            } 
            post{
                always{
                    echo "analysing code"
                }
            }
        }
        stage('Security Scan'){
            steps{
                echo "Perform a security on the code using the 'Nmap' security tool to identify any vulnerabilities"
            } 
                
        }
        stage('Deploy to Staging'){
            steps{
                echo "Deploy the action to the staging server AWS EC2"

        }
        stage('Integration Tests on Staging')
            steps{
                echo "Run integration tests on the staging environment"
                echo "$PRODUCTION_ENVIRONMENT, deployment is done"
            } 
            post{
                always{
                    echo "Run integration tests $PRODUCTION_ENVIRONMENT"
        }
        stage('Deploy to Production'){
            steps{
                echo "Deploying the application to the AWS EC2 Production server"
                echo "$PRODUCTION_ENVIRONMENT, deployment is done"
            } 
            post{
                always{
                    echo "Deployed to production $PRODUCTION_ENVIRONMENT"
                }
            }
        }
    }
}
    }
}