pipeline{
    agent {
        label{
            label 'wakanda'
        }
    }
    stages{
        stage('main-branch-deploy'){
            when{
                branch 'main'
            }
            steps{
                checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[credentialsId: 'github-id', url: 'https://github.com/festuge/secon-practoce-multi.git']]])
            }
        }
        stage('develop-branch-delpoy-code'){
            when{
                branch 'develop'
            }
            steps{
                sh 'echo "this is main branch deployment"'
                sh ' cat /etc/passwd'
            }
        }
        stage('main-branch-deployment-code'){
            when{
                branch 'main'
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
