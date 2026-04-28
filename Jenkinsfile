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
                        }
                    }
                    steps {
                        sh 'echo Running the Integration Test...'
                    }
                }

            }
        }
    }
}
