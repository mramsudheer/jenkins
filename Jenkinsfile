pipeline{
    agent {
        node{
            label 'ROBOSHOP'
        }
    }
    environment{
        COURSE = "Jenkins"
    }
    options{
        disableConcurrentBuilds()
        timeout(time: 5, unit: 'SECONDS')
    }
    stages{
        stage('Build'){
            steps{
                script{
                    sh """
                        echo "build"
                        echo $COURSE
                        sleep 15
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