pipeline {
    agent any
    stages {
        stage('Clone') {
            steps{
                git 'https://github.com/felipealvarezaguirre/ui-selenium-tests.git'
            }
        }
        stage('Test') {
            steps{
                sh 'mvn clean test'
            }
        }
    }
    post {
        always {
            junit 'target/surefire-reports/*.xml'
        }
    }
}