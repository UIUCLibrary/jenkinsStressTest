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
                            steps{
                                bat "dir"
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