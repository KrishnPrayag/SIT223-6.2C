pipeline
{
    agent any
    environment
    {
        DIRECTORY_PATH = "C:/Krishn/Docs"
        AUTOMATION_TOOL = "Maven"
        TESTING_ENVIRONMENT = "TEST"
        PRODUCTION_ENVIRONMENT = "AWS EC2"
    }
    stages
    {
        stage('Build')
        {
            steps
            {
                echo "Fetch the source code from $DIRECTORY_PATH"

                echo "Compile the code using $AUTOMATION_TOOL "
            }
        }
        stage('Unit and Integration Tests')
        {
            steps {
                echo 'Running unit and integration tests using Citrus'
            }
            post{
                    success{
                        emailext subject: 'Unit and Integration Tests status',
                            body: "The Unit and Integrations Test are a Success!",
                            to: 'krishnprayag.kp@gmail.com'
                        }
                    failure{
                        emailext 
                                body: "The Unit and Integrations Test are a Failure!",
                                 attachLog: true,
                                 subject: 'Unit and Integration Tests status',
                                 to: 'krishnprayag.kp@gmail.com',
                                 
                        }
                }
        }
        stage('Code Analysis')
        {
            steps
            {
                echo "Check the quality of the code using SonarQube"
            }
        }
        stage('Security Scan')
        {
            steps
            {
                echo "Pass the code to Veracode for Security Scan"
            }
            post{
                    success{
                        emailext( subject: 'Security Scans status',
                            
                                body: "The Security scans are a Success!",
                                attachLog: true,
                                to: 'krishnprayag.kp@gmail.com',
                                 )
                        }
                    failure{
                        emailext (subject: 'Security Scans status',
                            body: "The Security scans are a Failure!",
                            attachLog: true,
                            to: 'krishnprayag.kp@gmail.com',
                                  )
                        }
                }
        }
        stage('Deploy to Staging')
        {
            steps
            {
                echo 'Deploy the code to Google Compute Engine for staging'
            }
        }
        stage('Integration Tests on Staging')
        {
            steps
            {
                echo 'Run integration tests using Cypress and TestNG'
            }
            post{
                    success{
                        emailext (subject: 'Integration Tests on Staging status',
                            to: 'krishnprayag.kp@gmail.com',
                            body: "Integration Tests on Staging are a Success!",
                            attachLog: true,
                                  )
                        }
                    failure{
                        emailext( subject: 'Integration Tests on Staging status',
                            to: 'krishnprayag.kp@gmail.com',
                            body: "Integration Tests on Staging are a Failure!",
                            attachLog: true,
                                 )
                        }
                }
        }
        stage('Deploy to Production')
        {
            steps
            {
                echo "THE PRODUCTION OF $PRODUCTION_ENVIRONMENT CAN START"
            }
        }
    }
}
