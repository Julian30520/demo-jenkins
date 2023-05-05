pipeline {
    agent any
    options {
        skipDefaultCheckout()
    }
    stages {
        stage('SCM') {
            steps {
                checkout scm
            }
        }
        stage('Build') {
            parallel {
                stage('Convert workspace path to absolute') {
                    steps {
                        script {
                            env.WORKSPACE = pwd()
                        }
                    }
                }
                stage('Compile') {
                    agent {
                        docker {
                            image 'maven:3.6.0-jdk-8'
                            reuseNode true
                            args "-v ${env.WORKSPACE}:/workspace"
                        }
                    }
                    steps {
                        bat 'cd /workspace && mvn clean compile'
                    }
                }
            }
        }
    }
}
