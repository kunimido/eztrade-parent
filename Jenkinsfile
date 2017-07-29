pipeline {
    agent any

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

    post {
        success {
            build job: "/eztrade/eztrade-model/${env.BRANCH_NAME}", wait: false
            build job: "/eztrade/eztrade-service-parent/${env.BRANCH_NAME}", wait: false
        }
    }
}