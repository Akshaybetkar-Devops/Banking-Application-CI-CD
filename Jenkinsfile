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
            emailext(
                subject: "SUCCESS - ${env.JOB_NAME} #${env.BUILD_NUMBER}",
                body: """
Hello,

The Banking Application CI/CD Pipeline completed successfully.

Project : ${env.JOB_NAME}
Build : ${env.BUILD_NUMBER}
Status : SUCCESS

Build URL:
${env.BUILD_URL}

Regards,
Jenkins
""",
                to: "akshaybetkar06@gmail.com"
            )
        }

        failure {
            emailext(
                subject: "FAILED - ${env.JOB_NAME} #${env.BUILD_NUMBER}",
                body: """
The Banking Application CI/CD Pipeline failed.

Project : ${env.JOB_NAME}
Build : ${env.BUILD_NUMBER}

Check:
${env.BUILD_URL}
""",
                to: "akshaybetkar06@gmail.com"
            )
        }
    }
}
