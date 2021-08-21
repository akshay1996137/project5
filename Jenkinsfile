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
                withSonarQubeEnv('SonarQube') {
                sh 'mvn sonar:sonar'
                }
            }
        }
        stage('deploy') {
            steps {
                withSonarQubeEnv('SonarQube') {
                sh 'mvn sonar:sonar'
                }
            }
        }
        stage('package') {
            steps {
                sh 'mvn package'
            }
        }


    }
}
