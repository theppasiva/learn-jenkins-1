pipeline {
    agent {
        node {
            label "AGENT-1"
        }
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
                echo "deploy"
            }
        }
        stage("checkin"){
            steps{
                echo "checkin"
            }
        }
    }
}