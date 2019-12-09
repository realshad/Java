pipeline{
    agent any
    environment{
        PASS= credentials('registry-pass')
    }
    stages{
        stage("Build"){
            steps{
                sh "echo Building"
            }
            
        }
        stage("Test"){
            steps{
                sh "echo Testing"
            }
            post {
                success{
                    sh "echo $PASS"
                }
            }
            
        }
        stage("Pushing"){
            steps{
                sh "echo Pushing"
            }
            
        }
    }
}