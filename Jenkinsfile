pipeline {
    agent any

    options {
        buildDiscarder(logRotator(numToKeepStr: '10'))
    }

    tools {
        jdk 'JDK 1.8'
        maven 'Maven 3.5.0'
    }

    stages {
        stage('Maven build') {
            steps {
                sh 'mvn -B -V -U clean install'
            }
        }
    }
}