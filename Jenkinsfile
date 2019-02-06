pipeline {
    agent none

    stages {
        stage("Test 1"){
            parallel{
                stage("Running on lib-jenkins-win-2016"){
                    agent {
                        label "lib-jenkins-win-2016"
                    }
                    stages{
                        stage("dummy"){
                            environment {
                                PATH = "${tool 'CPython-3.6'};PATH"
                            }
                            steps{
                                bat "dir"
                                // timeit -r 5 -s "import fib" "fib.F(33)"
                            }
                            
                        }
                    }
                }
                stage("Running on lib-win-docker"){
                    agent {
                        label "Docker"
                    }
                    stages{
                        stage("dummy"){
                            steps{
                                bat "dir"
                            }
                            
                        }
                    }
                }
            }
        }
    }
}