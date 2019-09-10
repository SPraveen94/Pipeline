pipeline {
  agent any
  stages {
          stage ( 'one'){
              steps{
                    echo ' Hi this is Stage 1'
                   }

          }
stage ( 'Two' ){
              steps{
                    input( 'Do you want to prceed?' )
                   }

          }
stage ( 'three' ){
             when{
               not{
                    branch "master"
                   }
             }
              steps{
                    echo ' Hello '
                   }

          }

stage ( 'Four' ){
             parallel{
               stage('Unit Test'){
                    steps{
                             echo "Running the unit test...."
                             }
                   }
             }
              stage('Integration Test'){
                    agent {
                            docker {
                                    reuseNode false
                                    image 'ubuntu'
                                  

                                 }


                      }
                       steps{
                             echo "Running the unit test...."
                             }
                   }
             }
}
}
}
}
}

