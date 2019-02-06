pipeline {
    agent none

    stages {
        stage("Suff"){
            parallel{
                stage("Dummy"){
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