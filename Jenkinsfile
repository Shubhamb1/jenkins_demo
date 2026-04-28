pipeline {
    agent any

    stages {

        stage('One') {
            steps {
                echo 'Hi, this is Shubham from Edureka'
            }
        }

        stage('Two') {
            steps {
                input 'Do You Want To Proceed?'
            }
        }

        stage('Three') {
            when {
                not {
                    branch 'master'
                }
            }
            steps {
                echo "Hello"
            }
        }

        stage('Four') {
            parallel {

                stage('Unit Test') {
                    steps {
                        echo "Running Unit Test Cases"
                    }
                }

                stage('Integration Test') {
                    agent {
                        docker {
                             image 'ubuntu'
                             reuseNode false
                             args '''
                                -v /mnt/c/ProgramData/Jenkins/.jenkins/workspace:/workspace
                                -w /workspace
                             '''
                        }
                    }
                    steps {
                        echo 'Running the Integration Test...'
                    }
                }

            }
        }
    }
}
