pipeline
{
    agent any
    stages
    {
        stage('Download')
        {
            steps
            {
                git 'https://github.com/sai89850/maven.git'
            }
        }
        stage('Build')
        {
            steps
            {
               sh  'mvn package'
            }
        }
        stage('Deployment')
        {
            steps
            {
                sh 'scp /var/lib/jenkins/workspace/DeclarativePipeline2/webapp/target/webapp.war ubuntu@13.60.183.15:/var/lib/tomcat10/webapps/testapp.war'
            }
        }
        stage('Testing')
        {
            steps{
            git 'https://github.com/sai89850/FunctionalTesting.git'
            sh 'java -jar /var/lib/jenkins/workspace/DeclarativePipeline2/testing.jar'
            }
        }
        stage('Delivery')
        {
            steps
            {
                sh 'scp /var/lib/jenkins/workspace/DeclarativePipeline2/webapp/target/webapp.war ubuntu@16.16.241.43:/var/lib/tomcat10/webapps/prodapp.war'
            }
        }
    }
}
