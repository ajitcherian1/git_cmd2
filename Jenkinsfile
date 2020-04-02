pipeline {
      agent any 
            stages{
                 stage ('One') {
                    steps {
                         echo 'hi this is ajit'
                               }    
                   } 
                 stage ('Two') { 
                    steps { 
                          input('Do you want to proceed?') 
                          } 
                                }                               
                  stage ('Three') {
                                     when { 
                                            not { 
                                                  branch 'master'
                                                }
                                             }
                                steps { 
                                      echo 'hello'
                                       }
                      }
                 stage('Four') {
                   parallel {
               stage('Unit Test') {
              steps {
           echo "Running the unit test...."   
}
} 
stage('Integration test') {
    agent { 
 docker {
 reuseNode false
 image 'ubuntu'
}

 }
steps {
   echo "running the integration test..."
}
}
  }
}
                    }
}
}

