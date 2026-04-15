pipeline {
    agent any

    tools {
        gradle 'Gradle8'
        jdk 'Java21'
    }

    stages {

        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/Cipherun/GradleApp.git'
            }
        }

        stage('Build') {
            steps {
                sh 'gradle clean build -x test'  // Skip tests
            }
        }

        stage('Test') {
            steps {
                echo 'Tests skipped in this build'
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
