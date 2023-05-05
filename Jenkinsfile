pipeline {
    agent any
    tools {
        maven 'maven'
    }

    stages {
        stage('Test') {
            steps {
                bat 'mvn test'
            }

            post {
                always {
                    junit 'target/surefire-reports/*.xml'
                }
            }
        }
        stage('Build') {
            steps {
                bat 'mvn clean package'
            }
        }
    }
}
