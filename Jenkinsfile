pipeline{
    agent {
        label{
            label 'wakanda'
        }
    }
    stages{
        stage('feature-branch-deploy-code'){
            when{
                branch 'feature'
            }
            steps{
                sh 'bash -x claudi.sh'
            }
        }
        stage('main-branch-delpoy-code'){
            when{
                branch 'main'
            }
            steps{
                sh 'echo "this is main branch deployment"'
                sh ' cat /etc/passwd'
            }
        }
        stage('develop-branch-deployment-code'){
            when{
                branch 'develop'
            }
            steps{
                sh 'cat /etc/passwd'
            }
        }
        stage('parallel-level'){
            parallel{
                stage('sub-job0'){
                    steps{
                        echo "sub-job-0"
                    }
                }
            }
        }
        stage('simple-cpu-check'){
            agent{
                label{
                    label 'blackpanther'
                }
            }
            steps{
                sh 'lsblk'
            }
        }
    }
}