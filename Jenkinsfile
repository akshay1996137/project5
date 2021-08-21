pipeline {
    agent any

    stages {
        stage('compile') {
            steps {
                echo 'compiling..'
                sh 'mvn compile'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
                sh 'mvn test'
            }
        }
        stage('sonar scan') {
            steps {
                withSonarQubeEnv('My SonarQube Server') {
                sh 'mvn sonar:sonar'
                }
            }
        }
    }
}
