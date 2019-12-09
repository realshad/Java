pipeline{
    agent any
    environment{
        PASS= credentials("registry-pass")
        
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
                    // sh "echo $BRANCH"
                }
            }
            
        }
        stage("Pushing"){
            when {branch 'release'}
            steps{
                sh "echo This is executed because of commit in release branch"
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