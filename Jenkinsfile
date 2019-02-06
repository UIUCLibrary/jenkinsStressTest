pipeline {
    agent none
    options {
        timestamps
    }
    stages {
        stage("Test 1"){
            parallel{
                stage("Running on lib-jenkins-win-2016"){
                    agent {
                        label "lib-jenkins-win-2016"
                    }
                    stages{
                        stage("Fibonacci test on lib-jenkins-win-2016"){
                            environment {
                                PATH = "${tool 'CPython-3.6'};${PATH}"
                            }
                            steps{
                                // bat 'python -m timeit -r 5 -s "import fib" "fib.F(33)'
                                bat 'python -m timeit -r 5 -s "import fib" "for i in range(32): print(fib.F(i))"'
                            }
                            
                        }
                    }
                }
                stage("Running on lib-win-docker"){
                    agent {
                        label "Docker"
                    }
                    stages{
                        stage("Fibonacci test on lib-win-docker"){
                            environment {
                                PATH = "${tool 'CPython-3.6'};${PATH}"
                            }
                            steps{
                                bat 'python -m timeit -r 5 -s "import fib" "for i in range(32): print(fib.F(i))"'
                                
                            }
                            
                        }
                    }
                }
            }
        }
    }
}