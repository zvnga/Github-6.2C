pipeline{
    agent any
    environment {
        DIRECTORY_PATH= "/Users/zungasiakalima/.jenkins/workspace/my_first_pipeline"
        TESTING_ENVIRONMENT= "my_first_pipeline"
        PRODUCTION_ENVIRONMENT= "Zunga"
    }
    stages{
        stage('Build'){
            steps{
                echo "Build sorted and completed!"
                echo "$DIRECTORY_PATH"
            } 
            post{
                always{
                    echo "fetch the source code from the directory path specified by the environment variable"
                    echo "compile the code and generate any necessary artifacts"
                }
            }
        }
        stage('Test'){
            steps{
                echo "Test sorted and completed!"
                echo "$TESTING_ENVIRONMENT"
            } 
            post{
                always{
                    echo "unit tests"
                    echo "integration tests"
                }
            }
        }
        stage('Code Quality Check'){
            steps{
                echo "Code Quality Check sorted and completed!"
            } 
            post{
                always{
                    echo "check the quality of the code"
                }
            }
        }
        stage('Deploy'){
            steps{
                echo "Deploy sorted and completed!"
            } 
            post{
                always{
                    echo "deploy the application to a testing environment specified by the environment variable"
                }
            }
        }
        stage('Aproval'){
            steps{
                echo "Aproval sorted and completed!"
            } 
            post{
                always{
                    sleep 10
                }
            }
        }
        stage('Deploy to Production'){
            steps{
                echo "Deploy to Production sorted and completed!"
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
