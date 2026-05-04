pipeline{
    agent {
        node{
            label 'ROBOSHOP'
        }
        environment{
            COURSE = "Jenkins"
        }
    }
    stages{
        stage('Build'){
            steps{
                script{
                    sh """
                        echo "build"
                        echo $COURSE
                    """
                }
            }
        }
        stage('Test'){
            steps{
                script{
                    sh """
                        echo "Testing"
                    """
                }
            }
        }
        stage('Deploy'){
            steps{
                script{
                    sh """
                        echo "Deploying"
                    """
                }
            }
        }
    }
    post{
        always{
            echo "I Will executes always post all Stages"
        }
    }
}