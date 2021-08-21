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
        stage(deploy') {
            steps {
                 nexusArtifactUploader artifacts: [[artifactId: 'WebAppCal', classifier: '', file: 'CI-CD5/target/WebAppCal-0.0.9.war', type: 'war']], credentialsId: 'nexus_id', groupId: 'com.web.cal', nexusUrl: '52.199.45.109:8081', nexusVersion: 'nexus2', protocol: 'http', repository: 'releases', version: '0.0.9'
            }
        }



    }
}
