pipeline{
    agent any
    stages{
        stage('feature branch deploy code'){
            when{
                branch 'feature'
            }
            steps{
                sh 'claudi.sh'
            }
        }
        stage('main branch delpoy code'){
            when{
                branch 'main'
            }
            steps{
                sh 'echo "this is main branch deployment"'
                sh ' cat /etc/passwd'
            }
        }
        stage('develop branch deployment code'){
            when{
                branch 'develop'
            }
            steps{
                sh 'cat claudi.sh'
            }
        }
        stage('parallel level'){
            paralle{
                stage('sub-job0'){
                    steps{
                        echo "sub job 0"
                    }
                }
            }
        }
        stage('simple-cpu-check'){
            steps{
                sh 'lscpu'
            }
        }
    }
}