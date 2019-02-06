pipeline {
    agent none

    stages {
        stage("Test 1"){
            parallel{
                stage("Dummy"){
                    agent {
                        label "lib-jenkins-win-2016"
                    }
                    steps{
                        echo "hello"
                    }
                }
                stage("Dummy2"){
                    steps{
                        echo "hello"
                    }
                }
            }
        }
    }
}