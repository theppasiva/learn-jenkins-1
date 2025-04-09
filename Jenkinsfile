pipeline {
    agent {
        node {
            label 'AGENT-1'
        }
    }
    environment {
        GREETING = 'Hello jenkins'

    }
    options {
        timeout(time: 1, unit: 'SECONDS')
        disableConcurrentBuilds() 
    }
    parameters {
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')

        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')

        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')

        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')

        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
    }
    stages {
        stage("build"){
            steps {
                echo "Building"
            }
        }
        stage("test") {
            steps {
                echo "testing"
            }
        }
        stage("deploy") {
            steps {
                sh """
                echo 'Here I write shell script'
                #env
                #ls -la
                #df -h
                """
                echo "$GREETING"
                // #sleep 30
                
            }
        }
        stage('Check params') {
            steps {
                sh '''
                echo "Hello ${params.PERSON}"

                echo "Biography: ${params.BIOGRAPHY}"

                echo "Toggle: ${params.TOGGLE}"

                echo "Choice: ${params.CHOICE}"

                echo "Password: ${params.PASSWORD}"
                '''
            }
        }
        
    }
    post { 
        always { 
            echo 'I will always say Hello again!'
        }
        failure { 
            echo 'this runs when pipeline is failed, used generally to send some alerts'
        }
        success { 
            echo 'I will  say Hello when pipeline is success'
        }
    }
}