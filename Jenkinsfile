pipeline {
    agent any

    tools {
        jdk 'JDK 1.8'
        maven 'Maven 3.3.9'
    }

    stages {
        stage('Maven build') {
            steps {
                sh 'mvn -B clean install'
            }
        }
    }

    post {
        success {
            build job: "/eztrade/eztrade-service-parent/${env.BRANCH_NAME}", wait: false
        }
    }
}