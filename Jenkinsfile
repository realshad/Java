pipeline {

    agent any
       
    stages {

        stage('Build') {
            steps {
                sh ' echo "Building" '
            }

            post {
                success {
                  sh ' echo "Sonar" '
                }
            }
        }

        stage('Test') {
            steps {
                sh 'echo "testing"'
            }

            post {
                always {
                    sh 'echo "junit"'
                }
            }
        }

        stage('Push') {
            steps {
                sh 'echo "pushing"'
            }
        }

        stage('Deploy') {
            steps {
                sh 'echo "deploying"'
            }
        }
    }
}
