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
                df -h
                """
                echo "$GREETING"
                // #sleep 30
                
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