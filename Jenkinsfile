pipeline {
    agent {
        tools {
           maven "maven"
        }
    }
    stages {
        stage('Build') {
            steps {
                bat 'mvn clean compile'
            }
        }
    }
}
