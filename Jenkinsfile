pipeline {
    agent any

    environment {
        // Set JAVA_HOME and MAVEN_HOME directly
        JAVA_HOME = C:\Program Files\Java\jdk-25.0.2
        MAVEN_HOME = C:\Apache\maven\apache-maven-3.9.12
        PATH = "${env.JAVA_HOME}\\bin;${env.MAVEN_HOME}\\bin;${env.PATH}"
    }

    stages {
        stage('Checkout') {
            steps {
                git https://github.com/abhishek24-06/Abhishek-WebApp-using-Xampp
            }
        }

        stage('Build') {
            steps {
                bat 'mvn clean install'
            }
        }

        stage('Test') {
            steps {
                bat 'mvn test'
            }
        }
    }

    post {
        success {
            echo '✅ Build and tests succeeded!'
        }
        failure {
            echo '❌ Build or tests failed!'
        }
    }
}