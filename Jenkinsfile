pipeline
{
    agent any
    tools
    {
        maven 'MAVEN'
    }
    stages
    {
        stage('Checkout stage')
        {
            steps
            {
                checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/brakeshdevops/javap.git']]])
            }
        }
        stage('Build Stage')
        {
            steps
            {
                sh 'mvn -Dmaven.test.failure.ignore-true clean package'
            }
        }
    }
}