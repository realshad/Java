pipeline{
    agent any
    environment{
        PASS= credentials('registry-pass')
    }
    stages{
        stage("Build"){
            steps{
                sh "./jenkins/build/build.sh"
            }
            
        }
        stage("Test"){
            steps{
                sh "./jenkins/test/mvn.sh"
            }
            post {
                success{
                    sh "echo $PASS"
                }
            }
            
        }
        stage("Pushing"){
            steps{
                sh "./jenkins/push/push.sh"
            }
            
        }
        stage("Deploy"){
            steps{
                sh "./jenkins/deploy/deploy.sh"
            }
        }
    }
}