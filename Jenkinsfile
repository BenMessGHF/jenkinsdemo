pipeline {
    agent any

    credentials {
        usernamePassword(
            credentialsId: 'github-credentials',
            username: 'BenMessGHF',
            password: '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'
        )
    }
    stages {
        stage('Checkout') {
            steps {
                // Checkout the code from the repository
                git 'https://github.com/BenMessGHF/jenkinsdemo.git'
            }
        }

        stage('Build') {
            steps {
                // Build the Spring Boot application
                sh './mvnw clean install'
            }
        }

        stage('Test') {
            steps {
                // Run the tests
                sh './mvnw test'
            }
        }

        stage('Package') {
            steps {
                // Package the application
                sh './mvnw package'
            }
        }

    }

    post {
        success {
            echo 'Pipeline succeeded!'
        }
        failure {
            echo 'Pipeline failed!'
        }
    }
}