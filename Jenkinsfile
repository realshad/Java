pipeline{
    agent any
    environment{
        PASS= credentials('registry-pass')
    }
    stages{
        stage("Build"){
            steps{
                sh 'chmod +x ./jenkins/build/build.sh '
                sh "./jenkins/build/build.sh"
            }
            
        }
        stage("Test"){
            steps{
                sh 'chmod +x ./jenkins/test/mvn.sh '
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
                sh 'chmod +x ./jenkins/push/push.sh '
                sh "./jenkins/push/push.sh"
            }
            
        }
        stage("Deploy"){
            steps{
                sh 'chmod +x ./jenkins/deploy/deploy.sh '
                sh "./jenkins/deploy/deploy.sh"
            }
        }
    }
}