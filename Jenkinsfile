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
        timeout(time: 5, unit: 'MINUTES')
    }
    parameters{
        string(name: 'PERSON', defaultValue: 'Mr Rama Sudheer', description: 'Who should I say hello to?')
        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')
        booleanParam(name: 'DEPLOY', defaultValue: false, description: 'Toggle this value')
        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')
        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
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
                        echo "Hello ${params.PERSON}"
                        echo "Biography: ${params.BIOGRAPHY}"
                        echo "Toggle: ${params.TOGGLE}"
                        echo "Deploy: ${params.DEPLOY}" 
                        echo "Password: ${params.PASSWORD}"
                    """
                }
            }
        }
        stage('Deploy'){
            /*input{
                message "Please provide Deployment details"
                parameters{
                    booleanParam(name: 'DEPLOY', defaultValue: false)
                }
            }
            when{
                expression {
                    params.DEPLOY == true
                }
            } */
            /*input{
                message "Should we continue?"
                ok "Yes, we should"
                submitter "alice,bob"
                parameters{
                    string(name: 'PERSON', defaultValue: 'Rama', description: 'Who should I say Hello to?')
                }
            } */
            steps{
                def userInput = input(
                    message: "Should we Continue?",
                    parameters:[
                        choice(name:'DEPLOY_NOW', choices: ['true','false'], description: 'Deploy this build?')
                    ]
                )
                if(userInput == 'true'){
                    script{
                        sh """
                            echo "Deploying"
                        """
                    }
                }
                else{
                    sh """
                    echo "Deployment Aborted"
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