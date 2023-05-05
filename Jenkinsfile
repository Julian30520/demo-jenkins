pipeline {
    agent {
        docker {
            image 'maven:3.6.0-jdk-8-alpine'
            args '-v C:/ProgramData/Jenkins/.jenkins/workspace/projet-maven:/workspace'
            
            reuseNode true
        }
    }
    stages {
        stage('Build') {
            steps {
                sh 'mvn clean compile'
            }
        }
    }
}
