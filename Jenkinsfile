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
        stage('Test')
        {
            steps
            {
                echo "Unit Tests"
                echo "Integration Tests"
            }
        }
        stage('Code Quality Check')
        {
            steps
            {
                echo "Check the quality of the code"
            }
        }
        stage('Deploy')
        {
            steps
            {
                echo "deploy the application to $TESTING_ENVIRONMENT"
            }
        }
        stage('Approval')
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