pipeline{
    agent any
    stages{
        stage('1-clone'){
            steps{
                sh 'cat /etc/passwd'
            }
        }
        stage('2-parallel-jobs'){
            parallel{
                stage('1-subjob1'){
                    steps{
                        sh 'lscpu'
                    }
                }
                stage('2-subjob2'){
                    when{
                        branch 'feature'
                    }
                    steps{
                        sh 'df -h'
                    }
                }
            }
        }
        stage('3-codetest'){
            steps{
                sh "free -m"
            }
        }
        stage('4-closing'){
            when{
                branch "main"
            }
            steps{
                echo "Team4 branch project"
            }
        }
    }
}