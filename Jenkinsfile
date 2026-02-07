pipeline {
    agent any

    tools {
        jdk 'jdk17'       // The JDK name you configured in Jenkins
        maven 'maven'     // The Maven name you configured in Jenkins
    }

    stages {
        stage('Checkout') {
            steps {
                // Checkout the code from your GitHub repo
                git branch: 'main', url: 'https://github.com/lookism-12/student-management.git'
            }
        }

        stage('Build') {
            steps {
                echo 'Building the project...'
                sh 'mvn clean install'
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
                sh 'mvn test'
            }
        }
    }

    post {
        success {
            echo 'Build and tests completed successfully!'
        }
        failure {
            echo 'Build or tests failed!'
        }
    }
}
