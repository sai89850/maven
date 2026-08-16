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
<<<<<<< HEAD
                sh 'scp /var/lib/jenkins/workspace/DeclarativePipeline2/webapp/target/webapp.war ubuntu@13.60.35.109:/var/lib/tomcat10/webapps/testapp.war'
=======
                deploy adapters: [tomcat9(alternativeDeploymentContext: '', credentialsId: '9b4f91a2-f5ae-4dc8-b1b0-c2dfc68e9bd6', path: '', url: 'http://13.60.183.15:8080/')], contextPath: 'testapp', war: '**/*.war'
>>>>>>> 3de6ad82a9b888f21baaf72974eb6b7b9065981d
            }
        }
        stage('Testing')
        {
            steps{
            git 'https://github.com/sai89850/FunctionalTesting.git'
<<<<<<< HEAD
            sh 'java -jar /var/lib/jenkins/workspace/DeclarativePipeline2/testing.jar'
=======
            sh 'java -jar /var/lib/jenkins/workspace/DeclarativePipeline/testing.jar'
>>>>>>> 3de6ad82a9b888f21baaf72974eb6b7b9065981d
            }
        }
        stage('Delivery')
        {
            steps
            {
<<<<<<< HEAD
                sh 'scp /var/lib/jenkins/workspace/DeclarativePipeline2/webapp/target/webapp.war ubuntu@13.60.35.109:/var/lib/tomcat10/webapps/prodapp.war'
=======
                deploy adapters: [tomcat9(alternativeDeploymentContext: '', credentialsId: '9b4f91a2-f5ae-4dc8-b1b0-c2dfc68e9bd6', path: '', url: 'http://16.16.241.43:8080/')], contextPath: 'prodapp', war: '**/*.war'
>>>>>>> 3de6ad82a9b888f21baaf72974eb6b7b9065981d
            }
        }
    }
}
