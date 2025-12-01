# jenkins pipeline script -
pipeline {
    agent any
    tools { maven 'MAVEN3' }
    stages {
        stage('clean') {
            steps {
                git 'https://github.com/NitinSiddardha/maven_webapp.git'
                bat 'mvn clean'
            }
        }
        stage('install') {
            steps {
                bat 'mvn install'
            }
        }
    }
}
