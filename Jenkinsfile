pipeline {
        agent any
             stages {
                 stage('Checkout-git'){
                      steps {
                       git poll: true, url: 'https://github.com/nubializet/DOTT'    
                      }
                 }   
                 stage('Build') {
                      steps {

                        echo 'Build'
                           }
                 }
                     
                     

                      stage('Testing') {
                        steps {
                               echo 'Testing' 
                        }
                    }
                    stage('Deploy') {
                        steps {
                        echo 'Deploying'
                            }
                     }
                     
    }
}
