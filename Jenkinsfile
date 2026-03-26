pipeline {
    agent any
    stages {
        stage('Clone') {
            steps {
                git 'https://github.com/felipealvarezaguirre/ui-selenium-tests.git'
            }
        }
        stage('Test in Docker') {
            steps {
                script {
                    docker.image('maven:3.9.9-eclipse-temurin-17').inside {
                        sh 'mvn clean test'
                    }
                }
            }
        }
    }
    post {
        always {
            junit 'target/surefire-reports/*.xml'
        }
    }
}