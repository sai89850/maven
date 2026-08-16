pipeline {
    agent any

    stages {

        stage('Download') {
            steps {
                git 'https://github.com/sai89850/maven.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn package'
            }
        }

        stage('Deployment') {
            steps {
                deploy adapters: [
                    tomcat9(
                        alternativeDeploymentContext: '',
                        credentialsId: '9b4f91a2-f5ae-4dc8-b1b0-c2dfc68e9bd6',
                        path: '',
                        url: 'http://13.60.183.15:8080/'
                    )
                ],
                contextPath: 'testapp',
                war: '**/*.war'
            }
        }

        stage('Testing') {
            steps {
                dir('FunctionalTesting') {
                    git 'https://github.com/sai89850/FunctionalTesting.git'
                    sh 'mvn test'
                }
            }
        }

        stage('Delivery') {
            steps {
                deploy adapters: [
                    tomcat9(
                        alternativeDeploymentContext: '',
                        credentialsId: '9b4f91a2-f5ae-4dc8-b1b0-c2dfc68e9bd6',
                        path: '',
                        url: 'http://16.16.241.43:8080/'
                    )
                ],
                contextPath: 'prodapp',
                war: '**/*.war'
            }
        }
    }
}
