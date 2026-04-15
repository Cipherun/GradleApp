pipeline {
    agent any

    tools {
        gradle 'Gradle8'     // Change this to match your Jenkins Gradle tool name
        jdk 'Java21'         // Same JDK as your Maven pipeline
    }

    stages {

        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/Cipherun/MyGradleApp.git'
            }
        }

        stage('Build') {
            steps {
                sh 'gradle clean build'
            }
        }

        stage('Test') {
            steps {
                sh 'gradle test'
            }
        }

        stage('Run Application') {
            steps {
                echo 'Skipping runtime execution in CI pipeline'
            }
        }
    }

    post {
        success {
            echo 'Build successful!'
        }
        failure {
            echo 'Build failed!'
        }
    }
}
