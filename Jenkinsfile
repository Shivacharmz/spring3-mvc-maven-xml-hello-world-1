pipeline {
    agent any
    
    environment {
        MAVEN_HOME = tool 'Maven'
        PATH = "${env.MAVEN_HOME}/bin:${env.PATH}"
    }

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build') {
            steps {
                script {
                    sh "mvn clean package"
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    sh "mvn test"
                }
            }
        }

        stage('Deploy') {
            steps {
                // Add deployment steps if needed
            }
        }
    }

    post {
        always {
            cleanWs()
        }
    }
}
