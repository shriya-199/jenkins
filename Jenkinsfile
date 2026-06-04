pipeline {
    agent any

    tools {
        maven 'Maven3'
    }

    stages {
        stage('Checkout') {
            steps {
                echo 'Code checkout ho raha hai'
            }
        }

        stage('Build') {
            steps {
                bat 'mvn clean compile'
            }
        }

        stage('Test') {
            steps {
                bat 'mvn test'
            }
        }

        stage('Package') {
            steps {
                bat 'mvn package'
            }
        }

        stage('Archive Artifact') {
            steps {
                archiveArtifacts artifacts: 'target/*.jar', fingerprint: true
            }
        }

        stage('Docker Build') {
            steps {
                bat 'docker build -t jenkins-demo-app .'
            }
        }

        stage('Docker Run') {
            steps {
                bat 'docker run --rm jenkins-demo-app'
            }
        }
    }

    post {
        success {
            echo 'CI/CD Pipeline Successful'
        }
        failure {
            echo 'CI/CD Pipeline Failed'
        }
    }
}