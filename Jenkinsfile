pipeline {
   agent any
      stages {
            stage('One') {
                steps {
                    echo 'Hi, this is shubham fron edureka'
                      }
                         }
          
           stage('Two') {
                steps {
                       input('Do You Want To Proceed ?')
                      }
                        }
          
          stage('Three') {
                steps {
                       when{
                           not {
                                 branch "master"
                           }
                       }
                        step{
                            echo "Hello"
                        }
                      }
            stage('Four'){
                parallel
                {
                    stage('Unite Test'){
                        steps{
                            echo "Running Unit Test Cases"
                        }
                }  
                    stage('Intergration Test'){
                        agent {
                            docker{
                                reueNode false
                                image 'ubuntu'
                            }
                        }
                        steps{
                           echo 'Running the Intergration Test...'
                        }
                    }
            }
            }
          }
      }
}
