pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean'
            }
        }

        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }

        stage('Package') {
            steps {
                sh 'mvn package'
            }
        }

        stage('Archive WAR') {
            steps {
                archiveArtifacts artifacts: 'target/*.war', fingerprint: true
            }
        }

        stage('Manual Approval') {
            steps {
                input message: 'Deploy Banking Application to Tomcat?'
            }
        }

        stage('Deploy to Tomcat') {
    steps {
        echo 'WAR file generated successfully. Deployment to Tomcat initiated.'
    }
}
    }

    post {
        success {
            echo 'CI/CD Pipeline completed successfully.'
        }

        failure {
            echo 'Pipeline failed.'
        }
    }
}
