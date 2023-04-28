pipeline{
    agent any
    environment {
        DIRECTORY_PATH= "/Users/zungasiakalima/.jenkins/workspace/6.2 C 0 Github"
        TESTING_ENVIRONMENT= "6.2 C 0 Github"
        PRODUCTION_ENVIRONMENT= "Zunga"
    }
    stages{
        stage('Build'){
            steps{
                echo "Code has been built using Maven in order to compile and package it"
                echo "$DIRECTORY_PATH"
            } 
            post{
                always{
                    echo "Use Maven to copile and package code"
                    echo "compile the code and generate any necessary artifacts"
                }
            }
        }
        stage('Unit and Integration Tests'){
            steps{
                echo "Unit and Integration Tests completed ensuring code functions run as expected and applications work together "
                echo "$TESTING_ENVIRONMENT"
            } 
            post{
                success{
                    mail to: "agnuzzemail@gmail.com", 
                    subject: "Unit and Integration Status Email", 
                    body: "Unit and Integration was successful!", 
                    ${BUILD_LOG, maxLines, escapeHtml}
                }

            }
        }
        stage('Code Analysis'){
            steps{
                echo "Code Analysis completed using 'SonarQube' ensuring it meets industry standards "
            } 
            post{
                always{
                    echo "check the quality of the code"
                }
            }
        }
        stage('Security Scan'){
            steps{
                echo "Performed a security on the code using the 'Nmap' security tool to identify any vulnerabilities"
            } 
             post{
                success{
                    mail to: "agnuzzemail@gmail.com", 
                    subject: "Security Scan Status", 
                    body: "Security Scan was successful!"
                }
            }
        }
        stage('Deploy to Staging'){
            steps{
                echo "Deploying the action to the staging server AWS EC2!"
            } 
            post{
                always{
                    echo "Deploying action"
                }
            }
        }
        stage('Integration Tests on Staging'){
            steps{
                echo "Ran integration tests on the staging environment"
            } 
            post{
                success{
                    mail to: "agnuzzemail@gmail.com", 
                    subject: "Integration Test Status", 
                    body: "Integration Test Successful!"
                }
            }
        }
        stage('Deploy to Production'){
            steps{
                echo "Deploying the application to the AWS EC2 Production server"
                echo "$PRODUCTION_ENVIRONMENT, deployment is done"
            } 
            post{
                always{
                    echo "Deploy the code $PRODUCTION_ENVIRONMENT"
                }
            }
        }
    }
}
