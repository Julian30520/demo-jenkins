pipeline {
    agent any
  tools {
    maven 'maven'
  }

    stages {
        stage('Build') {
      steps {
        bat 'mvn clean compile'
      }
        }
        stage('SonarQube analysis') {
          steps {
            script {
            withSonarQubeEnv(installationName: 'sonar', credentialsId: 'jenkins-sonar-token') {
            bat 'mvn sonar:sonar'
            }
            }
          }
        }
    }
}
