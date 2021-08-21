pipeline {
    agent any
    stages {
        stage('test') {
            steps {
                sh 'mvn test'
            }
        
            post {
        
                 success {
                 mail bcc: '', body: 'success of test', cc: '', from: '', replyTo: '', subject: 'build test', to: 'akshaykatrojwar@gmail.com'
                 }

            }
        }
        stage('build') {
            steps {
                sh 'mvn package'
            }

            post {

                 success {
                 mail bcc: '', body: 'success of build', cc: '', from: '', replyTo: '', subject: 'build pass', to: 'akshaykatrojwar@gmail.com'
                 }

            }
        }


    }


   
}
