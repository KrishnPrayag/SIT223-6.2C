pipeline
{
    agent any
    environment
    {
        DIRECTORY_PATH = "FILES/FILES/CODE"
        TESTING_ENVIRONMENT = "TEST"
        PRODUCTION_ENVIRONMENT = "Krishn"
    }
    stages
    {
        stage('Build')
        {
            steps
            {
                echo "Fetch the source code from $DIRECTORY_PATH"

                echo "Compile the code and generate any necessary artefacts"
            }
        }
        stage('Unit and Integration Tests')
        {
            steps {
                echo 'Running unit and integration tests using JUnit and Selenium'
            }
            post{
                    always{
                        mail to: 'krishnprayag.kp@gmail.com',
                            subject: 'Unit and Integration Tests status',
                            body: "${currentBuild.result}: Job ",
                        attachLog: true)
                        }
                }
        }
        stage('Code Analysis')
        {
            steps
            {
                echo "Check the quality of the code"
            }
        }
        stage('Security Scan')
        {
            steps
            {
                echo "deploy the application to $TESTING_ENVIRONMENT"
            }
        }
        stage('Deploy to Staging')
        {
            steps
            {
                sleep 1
            }
        }
        stage('Integration Tests on Staging')
        {
            steps
            {
                sleep 10
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
